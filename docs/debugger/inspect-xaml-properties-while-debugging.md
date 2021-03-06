---
title: Просмотр свойств XAML во время отладки | Документы Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 390edde4-7b8d-4c89-8d69-55106b7e6b11
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: fcb2877a79afc310985102972d870caae560b393
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
ms.locfileid: "31480219"
---
# <a name="inspect-xaml-properties-while-debugging"></a>Просмотр свойств XAML во время отладки
Вы можете получить в режиме реального времени представление о выполнении кода XAML с **динамическое визуальное дерево** и **динамический обозреватель свойств**. Эти средства обеспечивают представление элементов пользовательского интерфейса выполняющегося приложения XAML в виде дерева, а также отображение свойств среды выполнения любого выбранного элемента интерфейса.  
  
 Эти средства можно использовать в следующих конфигурациях.  
  
|Тип приложения|Операционная система и средства|  
|-----------------|--------------------------------|  
|Приложения Windows Presentation Foundation (4.0 и более поздних версий)|Windows 7 и более поздних версий|  
|Универсальные приложения Windows|Windows 10 и более поздних версий, с [Windows 10 SDK](https://dev.windows.com/en-us/downloads/windows-10-sdk)|  
  
## <a name="looking-at-elements-in-the-live-visual-tree"></a>Просмотр элементов в динамическом визуальном дереве  
 Начнем с очень простого приложения WPF со списком и кнопкой. При каждом нажатии кнопки в список добавляется еще один элемент. Четные элементы показаны серым, а нечетные — желтым цветом.  
  
 Создайте новое приложение WPF C# (Файл > Создать > проект, а затем выберите C# и найдите приложение WPF). Назовите его **TestXAML**.  
  
 Измените файл MainWindow.xaml следующим образом.  
  
```xaml  
<Window x:Class="TestXAML.MainWindow"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    xmlns:local="clr-namespace:TestXAML"  
    mc:Ignorable="d"  
     Title="MainWindow" Height="350" Width="525">  
    <Grid>  
        <Button x:Name="button" Background="LightBlue" Content="Add Item" HorizontalAlignment="Left" Margin="216,206,0,0" VerticalAlignment="Top" Width="75" Click="button_Click"/>  
        <ListBox x:Name="listBox" HorizontalAlignment="Left" Height="100" VerticalAlignment="Top" Width="100" Margin="205,80,0,0"/>  
    </Grid>  
</Window>  
```  
  
 Добавьте следующий обработчик команд в файл MainWindow.xaml.cs:  
  
```csharp 
int count;

private void button_Click(object sender, RoutedEventArgs e)  
{  
    ListBoxItem item = new ListBoxItem();  
    item.Content = "Item" + ++count;  
    if (count % 2 == 0)  
    {  
        item.Background = Brushes.LightGray;  
    }  
    else  
    {  
        item.Background = Brushes.LightYellow;  
    }  
    listBox.Items.Add(item);  
}  
```  
  
 Выполните сборку решения и запустите отладку. (В качестве конфигурации сборки нужно выбрать отладку, а не выпуск. Дополнительные сведения о конфигурациях сборки см. в разделе [общее представление о конфигурациях построения](../ide/understanding-build-configurations.md).)  
  
 Когда окно, нажмите кнопку **добавить элемент** кнопку несколько раз. Результат должен быть примерно таким:  
  
 ![Главное окно приложения](../debugger/media/livevisualtree-app.png "LiveVIsualTree приложения")  
  
 Теперь откройте **динамическое визуальное дерево** окна (**Отладка > Windows > динамического визуального дерева**, или найдите его в левой части IDE). Перетащите его из закрепленного положения, чтобы можно было просмотреть это окно и **динамические свойства** рядом друг с другом. В **динамическое визуальное дерево** окна, разверните **ContentPresenter** узла. Он должен содержать узлы для кнопки и списка. Разверните список (а затем **ScrollContentPresenter** и **ItemsPresenter**) для поиска элементов списка. Окно должно выглядеть следующим образом:  
  
 ![ListBoxItems в динамическом визуальном дереве](../debugger/media/livevisualtree-listboxitems.png "LiveVisualTree ListBoxItems")  
  
 Вернитесь в окно приложения и добавьте еще несколько элементов. Вы увидите список появится больше элементов в **динамическое визуальное дерево**.  
  
 Теперь давайте взглянем на свойства одного из элементов списка. Выберите первый элемент списка в **динамическое визуальное дерево** и нажмите кнопку **Показать свойства** значок на панели инструментов. **Динамический обозреватель свойств** должны отображаться. Обратите внимание, что **содержимого** поле является «Item1» и **фона** поле является **#FFFFFFE0** (Светло-желтый). Вернитесь к **динамическое визуальное дерево** и выберите второй элемент списка. **Динамический обозреватель свойств** показывает, что **содержимого** поле является «Item2» и **фона** поле является **#FFD3D3D3** (светло-серый ).  
  
 Фактическая структура XAML-кода содержит много элементов, которые вы, вероятно, не интересует непосредственно, и если вы не знаете код также может быть сложно, навигация по дереву, чтобы найти то, что вы ищете. Поэтому **динамическое визуальное дерево** обеспечивает несколько способов, позволяющие использовать пользовательского интерфейса приложения для поиска элемента, которое необходимо исследовать.  
  
 **Разрешить выделение в выполняющемся приложении**. Этот режим можно включить, выбрав крайнюю левую кнопку на **динамическое визуальное дерево** инструментов. Этот режим включен, можно выбрать элемент пользовательского интерфейса в приложении и **динамическое визуальное дерево** (и **динамического обозревателя свойств**) автоматически обновляется для отображения узла в дереве, соответствующий этому элементу и его свойства.  
  
 **Отображение графических элементов макета в работающем приложении**. Этот режим можно включить при нажатии кнопки, расположенной справа от кнопки включения выделения. Когда **отображение графических элементов макета** имеет значение on, то окно приложения Показать горизонтальные и вертикальные линии вдоль границ выбранного объекта, чтобы можно было видеть, относительно чего он выровнен, а также прямоугольники, показывающие поля. Например, включите оба **Включение возможности выбора** и **формат вывода** и выберите **добавить элемент** блок текста в приложении. Должен появиться узел блока текста в **динамическое визуальное дерево** и свойства блока текста **динамического обозревателя свойств**, а также горизонтальные и вертикальные линии для границы текстового блока.  
  
 ![LivePropertyViewer в DisplayLayout](../debugger/media/livevisualtreelivepropertyviewer-displaylayout.png "LiveVisualTreeLivePropertyViewer DisplayLayout")  
  
 **Предварительный просмотр выбора**. Этот режим можно включить, нажав третью кнопка слева на панели инструментов динамического визуального дерева. Этот режим показывает XAML-код, где был объявлен элемент, если имеется доступ к исходному коду приложения. Выберите **Включение возможности выбора** и **Предварительный просмотр выбора**, а затем нажмите кнопку в тестируемом приложении. Файл MainWindow.xaml откроется в Visual Studio и курсор будет находится в строке, где определена кнопка.  
  
## <a name="using-xaml-tools-with-running-applications"></a>Использование средств XAML с работающими приложениями  
 Эти средства XAML можно использовать даже при отсутствии исходного кода. При подключении к выполняющемуся приложению XAML можно использовать **динамическое визуальное дерево** в элементах пользовательского интерфейса этого приложения слишком. Ниже приведен пример, с помощью же тестовое приложение WPF, которые использовались до.  
  
1.  Запуск **TestXaml** приложение в конфигурации выпуска. Не удается присоединить к процессу, который выполняется в **отладки** конфигурации.  
  
2.  Откройте второй экземпляр Visual Studio и нажмите кнопку **Отладка > присоединить к процессу**. Найти **TestXaml.exe** в списке доступных процессов и нажмите кнопку **присоединение**.  
  
3.  Начнется выполнение приложения.  
  
4.  Во втором экземпляре Visual Studio, откройте **динамическое визуальное дерево** (**Отладка > Windows > динамического визуального дерева**). Вы увидите **TestXaml** элементы пользовательского интерфейса и вы сможете изменять их, как во время отладки приложения напрямую.