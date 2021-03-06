---
title: 'Пошаговое руководство: Синхронизация настраиваемой области задач с кнопкой на ленте'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom task panes [Office development in Visual Studio], showing and hiding
- showing custom task panes
- Ribbon [Office development in Visual Studio], custom task panes
- toggle buttons [Office development in Visual Studio]
- custom task panes [Office development in Visual Studio], synchronizing with Ribbon button
- user interfaces [Office development in Visual Studio], custom task panes
- synchronization [Office development in Visual Studio], custom task panes
- task panes [Office development in Visual Studio], showing and hiding
- custom task panes [Office development in Visual Studio], creating
- hiding custom task panes
- task panes [Office development in Visual Studio], creating
- task panes [Office development in Visual Studio], synchronizing with Ribbon button
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7b6c36e93d9dd8dd4ef81d0d124ae33e842a16d7
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "35674841"
---
# <a name="walkthrough-synchronize-a-custom-task-pane-with-a-ribbon-button"></a>Пошаговое руководство: Синхронизация настраиваемой области задач с кнопкой на ленте
  В этом пошаговом руководстве демонстрируется создание настраиваемой области задач, пользователи могут скрывать и отображать, щелкая выключатель на ленте. Рекомендуется всегда создавать элемент пользовательского интерфейса, например кнопку, который пользователи могут нажать для отображения или скрытия настраиваемой области задач. Это необходимо по той причине, что приложения Microsoft Office не имеют встроенных средств для отображения и скрытия настраиваемых областей задач.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Хотя в этом пошаговом руководстве используется Excel, рассмотренная процедура применима к любым перечисленным выше приложениям.  
  
 В данном пошаговом руководстве рассмотрены следующие задачи:  
  
-   проектирование пользовательского интерфейса настраиваемой области задач;  
  
-   добавление выключателя на ленту;  
  
-   синхронизация выключателя с настраиваемой областью задач.  
  
> [!NOTE]  
>  Отображаемые на компьютере имена или расположения некоторых элементов пользовательского интерфейса Visual Studio могут отличаться от указанных в следующих инструкциях. Это зависит от имеющегося выпуска Visual Studio и используемых параметров. Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Excel или Microsoft [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)].  
  
## <a name="create-the-add-in-project"></a>Создание проекта надстройки  
 На этом шаге вы создадите проект надстройки VSTO для Excel.  
  
### <a name="to-create-a-new-project"></a>Создание нового проекта  
  
1.  Создайте проект надстройки Excel с именем **SynchronizeTaskPaneAndRibbon**с помощью шаблона проекта надстройки Excel. Дополнительные сведения см. в разделе [как: проектов Office, создайте в Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] откроет файл с исходным кодом **ThisAddIn.cs** или **ThisAddIn.vb** и добавит проект **SynchronizeTaskPaneAndRibbon** в **обозреватель решений**.  
  
## <a name="add-a-toggle-button-to-the-ribbon"></a>Добавление выключателя на ленту  
 Один из принципов проектирования приложений Office состоит в том, что пользователь всегда должен иметь возможность распоряжаться пользовательским интерфейсом приложения Office. Чтобы позволить пользователю управлять настраиваемой областью задач, можно добавить на ленту выключатель, который будет отображать и скрывать область задач. Чтобы создать выключатель, добавьте в проект элемент **Лента (визуальный конструктор)** . Конструктор помогает добавлять и размещать элементы управления, задавать их свойства и обрабатывать связанные с ними события. Дополнительные сведения см. в разделе [конструктор лент](../vsto/ribbon-designer.md).  
  
### <a name="to-add-a-toggle-button-to-the-ribbon"></a>Добавление выключателя на ленту  
  
1.  В меню **Проект** выберите пункт **Добавить новый элемент**.  
  
2.  В диалоговом окне **Добавление нового элемента** выберите элемент **Лента (визуальный конструктор)**.  
  
3.  Измените имя новой ленты на **ManageTaskPaneRibbon**и нажмите кнопку **Добавить**.  
  
     В конструкторе ленты откроется файл **ManageTaskPaneRibbon.cs** или **ManageTaskPaneRibbon.vb** и отобразятся вкладка и группа, используемые по умолчанию.  
  
4.  В конструкторе ленты щелкните группу **group1**.  
  
5.  В окне **Свойства** задайте для свойства **Label** значение **Диспетчер области задач**.  
  
6.  Перетащите элемент управления **ToggleButton** со вкладки **Элементы управления ленты Office**на **панели элементов** в группу **Диспетчер области задач** .  
  
7.  Нажмите **toggleButton1**.  
  
8.  В окне **Свойства** задайте в свойстве **Label** значение **Показать область задач**.  
  
## <a name="design-the-user-interface-of-the-custom-task-pane"></a>Проектирование пользовательского интерфейса настраиваемой области задач  
 Визуальный конструктор для настраиваемых областей задач не предусмотрен, но вы можете разработать собственный элемент управления с желаемой структурой. Далее в этом пошаговом руководстве вы добавите этот пользовательский элемент управления в настраиваемую область задач.  
  
### <a name="to-design-the-user-interface-of-the-custom-task-pane"></a>Проектирование пользовательского интерфейса настраиваемой области задач  
  
1.  В меню **Проект** выберите команду **Добавить пользовательский элемент управления**.  
  
2.  В диалоговом окне **Добавление нового элемента** измените имя пользовательского элемента управления на **TaskPaneControl**и нажмите кнопку **Добавить**.  
  
     Пользовательский элемент управления откроется в конструкторе.  
  
3.  Перетащите элемент управления **TextBox** со вкладки **Стандартные элементы управления**на **панели элементов** в пользовательский элемент управления.  
  
## <a name="create-the-custom-task-pane"></a>Создание настраиваемой области задач  
 Для создания настраиваемой области задач при запуске надстройки VSTO добавьте пользовательский элемент управления в область задач в обработчике событий <xref:Microsoft.Office.Tools.AddIn.Startup> надстройки VSTO. По умолчанию настраиваемая область задач не будет видима. Далее в этом пошаговом руководстве будет добавлен код, который будет отображать и скрывать область задач при нажатии выключателя, добавленного на ленту.  
  
### <a name="to-create-the-custom-task-pane"></a>Создание настраиваемой области задач  
  
1.  В **обозревателе решений**разверните **Excel**.  
  
2.  Щелкните правой кнопкой мыши файл **ThisAddIn.cs** или **ThisAddIn.vb** и выберите пункт **Просмотреть код**.  
  
3.  Добавьте следующий код в класс `ThisAddIn` . Этот код объявляет экземпляр класса `TaskPaneControl` членом класса `ThisAddIn`.  
  
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#1](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ThisAddIn.cs#1)]
     [!code-vb[Trin_TaskPaneRibbonSynchronize#1](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ThisAddIn.vb#1)]  
  
4.  Замените обработчик событий `ThisAddIn_Startup` следующим кодом. Этот код добавляет объект класса `TaskPaneControl` к полю `CustomTaskPanes` , но он не отображает настраиваемую область задач (по умолчанию свойство <xref:Microsoft.Office.Tools.CustomTaskPane.Visible%2A> класса <xref:Microsoft.Office.Tools.CustomTaskPane> имеет значение **false**). Кроме того, код Visual C# присоединяет обработчик событий к событию <xref:Microsoft.Office.Tools.CustomTaskPane.VisibleChanged> .  
  
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#2](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ThisAddIn.cs#2)]
     [!code-vb[Trin_TaskPaneRibbonSynchronize#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ThisAddIn.vb#2)]  
  
5.  Добавьте следующий метод в класс `ThisAddIn` . Этот метод обрабатывает событие <xref:Microsoft.Office.Tools.CustomTaskPane.VisibleChanged> . Когда пользователь нажимает кнопку **Закрыть** (X), чтобы закрыть область задач, этот метод обновляет состояние выключателя на ленте.  
  
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#3](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ThisAddIn.cs#3)]
     [!code-vb[Trin_TaskPaneRibbonSynchronize#3](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ThisAddIn.vb#3)]  
  
6.  Добавьте в класс `ThisAddIn` указанное ниже свойство. Оно предоставляет доступ к закрытому объекту `myCustomTaskPane1` другим классам. Позднее в этом руководстве мы добавим код к классу `MyRibbon` , который использует это свойство.  
  
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#4](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ThisAddIn.cs#4)]
     [!code-vb[Trin_TaskPaneRibbonSynchronize#4](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ThisAddIn.vb#4)]  
  
## <a name="hide-and-show-the-custom-task-pane-by-using-the-toggle-button"></a>Скрытие и отображение настраиваемой области задач с помощью выключателя  
 Заключительный шаг — добавить код, который будет отображать или скрывать настраиваемую область задач, когда пользователь щелкает выключатель на ленте.  
  
### <a name="to-display-and-hide-the-custom-task-pane-by-using-the-toggle-button"></a>Отображение или скрытие настраиваемой области задач с помощью выключателя  
  
1.  В конструкторе ленты дважды щелкните выключатель **Показать область задач** .  
  
     Visual Studio автоматически создает обработчик событий с именем `toggleButton1_Click`, который обрабатывает событие <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click> выключателя. Visual Studio также открывает *MyRibbon.cs* или *MyRibbon.vb* файл в редакторе кода.  
  
2.  Замените обработчик событий `toggleButton1_Click` следующим кодом. Когда пользователь щелкает выключатель, этот код показывает или скрывает настраиваемую область задач в зависимости от того, нажат ли выключатель.  
  
     [!code-vb[Trin_TaskPaneRibbonSynchronize#5](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ManageTaskPaneRibbon.vb#5)]
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#5](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ManageTaskPaneRibbon.cs#5)]  
  
## <a name="test-the-add-in"></a>Тестирование надстройки  
 При запуске этого проекта откроется приложение Excel. При этом настраиваемая область задач не отображается. Щелкните выключатель на ленте, чтобы проверить код.  
  
### <a name="to-test-your-vsto-add-in"></a>Для тестирования надстройки VSTO выполните следующие действия.  
  
1.  Нажмите клавишу **F5** для запуска проекта.  
  
     Убедитесь, что приложение Excel открылось и **Add-Ins** появится вкладка на ленте.  
  
2.  Нажмите кнопку **Add-Ins** вкладки на ленте.  
  
3.  В группе **Диспетчер области задач** щелкните выключатель **Показать область задач** .  
  
     Убедитесь в том, что область задач попеременно отображается и скрывается при нажатии выключателя.  
  
4.  Когда область задач будет видима, нажмите кнопку **Закрыть** (X) в углу области задач.  
  
     Убедитесь в том, что выключатель не нажат.  
  
## <a name="next-steps"></a>Следующие шаги  
 Дополнительные сведения о создании настраиваемых областей задач см. в следующих разделах:  
  
-   Создание настраиваемой области задач в надстройке VSTO для другого приложения. Дополнительные сведения о приложениях, поддерживающих настраиваемые области задач, см. в разделе [настраиваемых панелей задач](../vsto/custom-task-panes.md).  
  
-   Автоматизация приложения в настраиваемой области задач. Дополнительные сведения см. в разделе [Пошаговое руководство: автоматизации приложения с настраиваемой области задач](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md).  
  
-   Создание настраиваемой области задач для каждого сообщения электронной почты, открываемого в Outlook. Дополнительные сведения см. в разделе [Пошаговое руководство: отображение настраиваемых областей задач с сообщениями электронной почты в Outlook](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md).  
  
## <a name="see-also"></a>См. также  
 [Настраиваемые области задач](../vsto/custom-task-panes.md)   
 [Практическое: добавление настраиваемой области задач в приложение](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [Пошаговое руководство: Автоматизация приложения из настраиваемой области задач](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)   
 [Пошаговое руководство: Отображение настраиваемых областей задач с сообщениями электронной почты в Outlook](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md)   
 [Обзор ленты](../vsto/ribbon-overview.md)  
  
  