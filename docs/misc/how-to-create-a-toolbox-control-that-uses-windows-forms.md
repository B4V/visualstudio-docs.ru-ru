---
title: "Практическое руководство. Создание элемента управления панели элементов, использующего Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Элемент управления панели элементов"
  - "winforms"
  - "панель элементов"
ms.assetid: abbd3c3c-3a6e-4539-bd6c-a5891dead234
caps.latest.revision: 12
caps.handback.revision: 12
manager: "douge"
---
# Практическое руководство. Создание элемента управления панели элементов, использующего Windows Forms
Шаблон элемента управления панели элементов Windows Forms, включенный в [!INCLUDE[vssdk_dev11_long](../misc/includes/vssdk_dev11_long_md.md)], позволяет создавать элементы управления Windows Forms, которые автоматически добавляются в **панель элементов** при установке расширения. В этом разделе показано, как использовать шаблон для создания элемента управления **панели элементов**, который можно передавать другим пользователям.  
  
> [!NOTE]
>  Чтобы узнать, как загрузить пакет SDK для Visual Studio, посетите [Центр по разработке для расширяемости Visual Studio](http://go.microsoft.com/fwlink/?linkid=121964) на веб\-сайте MSDN.  
  
## Создание элемента управления панели элементов  
 С помощью шаблона элемента управления панели элементов Windows Forms создайте проект, а затем постройте пользовательский интерфейс в конструкторе.  
  
#### Создание проекта элемента управления панели элементов Windows Forms  
  
1.  В меню **Файл** последовательно выберите пункты **Создать** и **Проект**.  
  
2.  В диалоговом окне **создания проекта** в разделе **Установленные шаблоны** щелкните узел предпочтительного языка программирования, а затем выберите пункт **Расширяемость**. В списке типов проектов выберите пункт **Элемент управления панели элементов Windows Forms**.  
  
3.  В поле **Имя** введите имя, которое вы хотите использовать для проекта. Нажмите кнопку **ОК**.  
  
     Visual Studio создаст решение, которое содержит пользовательский элемент управления, атрибут для размещения этого элемента управления в **панели элементов** и манифест VSIX для развертывания.  
  
#### Создание пользовательского интерфейса элемента управления  
  
1.  В **обозревателе решений** дважды щелкните файл ToolboxControl.cs, чтобы открыть его в конструкторе.  
  
2.  Перетащите какие\-либо желаемые элементы управления из **панели элементов** в рабочую область конструирования и расположите их в соответствии с проектом.  
  
3.  В окне **Свойства** установите открытые свойства для пользовательского элемента управления и для дочерних элементов управления.  
  
## Кодирование элемента управления  
 По умолчанию элемент управления отображается в **панели элементов** как **ToolboxControl1** в группе элементов **панели элементов**, имя которой совпадает с именем решения. Эти имена можно изменить в файле ToolboxControl.cs.  
  
#### Кодирование элемента управления  
  
1.  В **обозревателе решений** щелкните правой кнопкой мыши файл ToolboxControl.cs и выберите пункт **Просмотреть код**, чтобы открыть этот файл в представлении кода.  
  
2.  В определении разделяемого класса, который реализует элемент управления, щелкните правой кнопкой мыши имя класса, выберите пункт **Рефакторинг**, а затем щелкните **Переименовать**. Измените имя класса на имя, которое будет отображаться в **панели элементов** после установки элемента управления.  
  
3.  Непосредственно над определением класса в объявлении атрибута `ProvideToolboxControl` измените значение первого параметра на имя группы элементов, в которой будет размещаться элемент управления в **панели элементов**.  
  
     В следующем примере показаны атрибут `ProvideToolboxControl` и скорректированное определение класса для элемента управления с именем `Counter` в группе элементов `General`.  
  
     [!code-cs[ToolboxControlWinForms#07](../misc/codesnippet/CSharp/how-to-create-a-toolbox-control-that-uses-windows-forms_1.cs)]  
  
4.  Реализуйте свойства, методы и события для этого элемента управления.  
  
## Сборка, тестирование и развертывание  
 При нажатии клавиши F5 выполняется сборка проекта, который включает VSIX\-файл развертывания, и открывается второй экземпляр Visual Studio с элементом управления, установленным в **панели элементов**.  
  
#### Сборка и тестирование элемента управления  
  
1.  Нажмите клавишу F5.  
  
2.  В новом экземпляре Visual Studio создайте проект приложения Windows Forms.  
  
3.  Найдите свой элемент управления в **панели элементов** и перетащите его в рабочую область конструирования.  
  
4.  В окне **Свойства** убедитесь, что свойства отображаются должным образом.  
  
5.  Добавьте какой\-либо код или дополнительные элементы управления, необходимые для тестирования методов и событий.  
  
6.  Нажмите клавишу F5, чтобы открыть приложение Windows Forms.  
  
7.  Убедитесь, что свойства, методы и события вашего элемента управления работают, как ожидалось.  
  
#### Развертывание элемента управления  
  
1.  После сборки протестированного проекта откройте папку \\bin\\debug\\ проекта в проводнике и найдите VSIX\-файл.  
  
2.  Отправьте VSIX\-файл в сеть или на веб\-сайт.  
  
     Если вы отправите файл на веб\-сайт [коллекции Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847), другие пользователи с помощью **диспетчера расширений** в Visual Studio смогут найти и установить этот элемент управления.  
  
## См. также  
 [Создание элементов управления WPF](../extensibility/creating-a-wpf-toolbox-control.md)