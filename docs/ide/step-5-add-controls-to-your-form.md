---
title: "Шаг 5. Добавление элементов управления в форму | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc2746f4-0b5c-4674-9ef7-f40f94150f52
caps.latest.revision: 20
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 07048d1ab89599609d7ece1e69056e6dd1dd7eea
ms.lasthandoff: 02/22/2017

---
# <a name="step-5-add-controls-to-your-form"></a>Шаг 5. Добавление элементов управления в форму
На данном шаге производится добавление в форму элемента управления `PictureBox` и элемента управления `CheckBox`. Затем на форму добавляются кнопки.  
  
 ![ссылка на видео](~/data-tools/media/playvideo.gif "воспроизвести_видео")Видеоверсию этой статьи см. на следующих страницах: [Tutorial 1: Create a Picture Viewer in Visual Basic - Video 2](http://go.microsoft.com/fwlink/?LinkId=205211) (Учебное руководство 1. Создание приложения для просмотра рисунков на Visual Basic — видео 2) или [Tutorial 1: Create a Picture Viewer in C# - Video 2](http://go.microsoft.com/fwlink/?LinkId=205200) (Учебное руководство 1. Создание приложения для просмотра рисунков на C# — видео 2). Эти видеоролики сняты с использованием более ранней версии Visual Studio, поэтому существуют небольшие различия в некоторых командах меню и других элементах пользовательского интерфейса. Однако концепции и процедуры аналогичны текущей версии Visual Studio.  
  
### <a name="to-add-controls-to-your-form"></a>Добавление элементов управления в форму  
  
1.  Перейдите на вкладку "Панель элементов" (находящуюся в левой части интегрированной среды разработки Visual Studio) и разверните группу **Стандартные элементы управления**. В результате этого действия отображается большая часть стандартных элементов управления, которые можно увидеть в формах.  
  
2.  Выберите элемент управления TableLayoutPanel в форме. Чтобы подтвердить, что элемент TableLayoutPanel выбран, убедитесь, что его имя отображается в раскрывающемся списке в верхней части окна **Свойства**. Выбирать элементы управления в форме можно также с помощью раскрывающегося списка в верхней части окна **Свойства**. Выбирать элементы управления таким образом зачастую проще, чем выбрать крошечный элемент управления с помощью мыши.  
  
3.  Дважды щелкните элемент **PictureBox**, чтобы добавить в форму элемент управления PictureBox. Поскольку элемент управления TableLayoutPanel закреплен так, чтобы заполнять собой форму, интегрированная среда разработки добавляет элемент управления PictureBox в первую пустую ячейку (левый верхний угол).  
  
4.  Щелкните новый элемент управления PictureBox, чтобы выбрать его, а затем щелкните черный треугольник на новом элементе управления PictureBox, чтобы отобразить его список задач, как показано на следующем рисунке.  
  
     ![Задачи элемента управления PictureBox](~/ide/media/express_pictureboxtasks.png "Express_PictureBoxTasks")  
Задачи элемента управления PictureBox  
  
    > [!NOTE]
    >  Если на TableLayoutPanel случайно был добавлен элемент управления неправильного типа, то его можно удалить. Щелкните элемент управления правой кнопкой мыши и в контекстном меню выберите **Удалить**. Удалять элементы управления из формы также можно с помощью строки меню. В строке меню выберите **Правка**, **Отменить** или **Правка**, **Удалить**.  
  
5.  Выберите ссылку **Закрепить в родительском контейнере**. В результате этого действия у элемента управления PictureBox свойство **Dock** принимает значение **Fill**. Чтобы это увидеть, выберите элемент управления PictureBox, перейдите в окно **Свойства** и убедитесь, что свойство **Dock** имеет значение **Fill**.  
  
6.  Сделайте так, чтобы элемент управления PictureBox занимал два столбца, изменив его свойство **ColumnSpan**. Выберите элемент управления PictureBox и установите для его свойства **ColumnSpan** значение **2**. Также необходимо, чтобы когда элемент управления PictureBox был пустым, отображалась пустая рамка. Установите для его свойства **BorderStyle** значение **Fixed3D**.  
  
    > [!NOTE]
    >  Если у PictureBox отсутствует свойство **ColumnSpan**, вероятно, элемент управления PictureBox был добавлен в саму форму, а не в элемент управления TableLayoutPanel. Чтобы исправить это, выберите элемент управления PictureBox, удалите его, выберите элемент TableLayoutPanel, а затем добавьте новый элемент управления PictureBox.  
  
7.  Выберите элемент управления TableLayoutPanel в форме и добавьте в нее элемент управления **CheckBox**. Двойным щелчком выберите элемент **CheckBox** на панели элементов, чтобы добавить новый элемент управления CheckBox в следующую свободную ячейку таблицы. Поскольку элемент управления PictureBox занимает первые две ячейки в TableLayoutPanel, элемент управления CheckBox добавляется в нижнюю левую ячейку. Выберите свойство **Text** и введите слово **Stretch**, как показано на следующем рисунке.  
  
     ![Элемент управления TextBox со свойством Stretch](~/ide/media/express_pictureviewercheckbox.png "Express_PictureViewerCheckbox")  
Элемент управления TextBox со свойством Stretch  
  
8.  Выберите в форме элемент управления TableLayoutPanel, а затем на панели элементов перейдите к группе **Контейнеры** (из которой был взят элемент управления TableLayoutPanel) и дважды щелкните элемент управления **FlowLayoutPanel**, чтобы добавить новый элемент управления в последнюю ячейку в элементе управления PictureBox (справа внизу). Затем закрепите FlowLayoutPanel в TableLayoutPanel (выбрав **Закрепить в родительском контейнере** в списке задач FlowLayoutPanel, раскрываемом с помощью черного треугольника, или установив свойству **Dock** FlowLayoutPanel значение **Fill**).  
  
    > [!NOTE]
    >  Элемент управления FlowLayoutPanel является контейнером, который размещает другие элементы управления аккуратно по строкам и в определенном порядке. Когда изменяется размер элемента управления FlowLayoutPanel, если он содержит достаточно места для размещения всех компонентов в одной строке, то он размещает их именно таким образом. В противном случае он размещает их по строкам одну над другой. Элемент управления FlowLayoutPanel будет использоваться для размещения четырех кнопок. Если кнопки при добавлении располагаются одна поверх другой, убедитесь, что перед добавлением кнопок вы выбрали FlowLayoutPanel. Хотя ранее было сказано, что каждая ячейка может содержать только один элемент управления, нижняя правая ячейка TableLayoutPanel содержит четыре элемента управления "Кнопка". Это так, потому что можно разместить элемент управления в ячейке, которая содержит другие элементы управления. Такой тип элементов управления называется "контейнер", и элемент управления FlowLayoutPanel является контейнером.  
  
### <a name="to-add-buttons"></a>Добавление кнопок  
  
1.  Выберите только что добавленный элемент управления FlowLayoutPanel. Перейдите к группе **Стандартные элементы управления** на панели элементов и двойным щелчком выберите элемент **Кнопка**, чтобы добавить в элемент управления FlowLayoutPanel кнопку с именем **button1**. Чтобы добавить другую кнопку, повторите это действие. Среда интегрированной разработки определяет, что уже существует кнопка с именем **button1**, и называет следующую кнопку как **button2**.  
  
2.  Обычно другие кнопки добавляются при помощи панели элементов. На этот раз выберите **button2**, затем в строке меню выберите **Правка**, **Копировать** (или нажмите сочетание клавиш CTRL+C). В строке меню выберите **Правка**, **Вставить** (или нажмите сочетание клавиш CTRL+V), чтобы вставить копию кнопки. Повторите вставку еще раз. Интегрированная среда разработки добавила кнопки **button3** и **button4** в FlowLayoutPanel.  
  
    > [!NOTE]
    >  Любой элемент управления можно копировать и вставлять. Среда интегрированной разработки именует и размещает новые элементы управления логическим образом. Если вставка элемента управления выполняется в контейнер, среда интегрированной разработки выбирает следующую логическую область для размещения.  
  
3.  Выберите первую кнопку и установите для ее свойства **Text** значение **Показать рисунок**. Затем установите для свойства **Text** следующих трех кнопок значения **Очистить рисунок**, **Установить цвет фона** и **Закрыть**.  
  
4.  Следующий шаг — задать размер кнопок и разместить их таким образом, чтобы они были выровнены по правой стороне панели. Выберите элемент управления FlowLayoutPanel и обратите внимание на его свойство **FlowDirection**. Измените его значение на **RightToLeft**. После этого действия кнопки должны сами выровняться по правой стороне ячейки и изменить свой порядок таким образом, чтобы кнопка **Показать рисунок** располагалась с правой стороны.  
  
    > [!NOTE]
    >  Если кнопки по-прежнему остаются в неправильном порядке, можно перетащить кнопки вокруг элемента управления FlowLayoutPanel для расположения их в произвольном порядке. Можно выбрать кнопку и перетащить ее влево или вправо.  
  
5.  Щелкните кнопку **Закрыть**, чтобы выбрать ее. Удерживая клавишу CTRL, щелкните три другие кнопки, чтобы все они были выбраны. При выделенных кнопках перейдите к окну **Свойства** и прокрутите его вверх до свойства **AutoSize**. Это свойство указывает кнопке автоматически изменять свой размер так, чтобы весь текст мог разместиться на ней. Задайте значение **true**. Кнопки теперь должны иметь соответствующий размер и быть расположены в правильном порядке. (Пока выделены все четыре кнопки, можно одновременно изменить все четыре свойства **AutoSize**.) На следующем рисунке показаны эти четыре кнопки.  
  
     ![Программа просмотра изображений с четырьмя кнопками](~/ide/media/express_autosize.png "Express_AutoSize")  
Программа просмотра изображений с четырьмя кнопками  
  
6.  Теперь снова запустите программу, чтобы увидеть обновленную компоновку формы. При нажатии кнопок и установке флажка пока ничего не происходит, однако вскоре все заработает.  
  
### <a name="to-continue-or-review"></a>Продолжить или повторить пройденный материал  
  
-   Следующий шаг руководства см. в разделе [Step 6: Name Your Button Controls](../ide/step-6-name-your-button-controls.md) (Шаг 6. Присвоение имен элементам управления "Кнопка").  
  
-   Предыдущий шаг руководства см. в разделе [Step 4: Lay Out Your Form with a TableLayoutPanel Control](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md) (Шаг 4. Создание макета формы с помощью элемента управления TableLayoutPanel).