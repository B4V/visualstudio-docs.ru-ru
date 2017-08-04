---
title: "Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 2"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "project items [SharePoint development in Visual Studio], creating template wizards"
  - "SharePoint project items, creating template wizards"
  - "SharePoint development in Visual Studio, defining new project item types"
ms.assetid: 2d8165d3-4af9-4a5e-bdba-8b2a06b1dc8d
caps.latest.revision: 44
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 43
---
# Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 2
  После того как пользовательский тип элемента проекта SharePoint определен и связан с шаблоном элемента в Visual Studio, имеет смысл также создать мастер для шаблона.  Этот мастер можно использовать для сбора информации от пользователей, когда они добавляют в проект новые экземпляры элемента проекта с помощью этого шаблона.  Собранные сведения могут быть использованы для инициализации элемента проекта.  
  
 Данное пошаговое руководство освещает добавление мастера к элементу проекта настраиваемого действия, как это показано в разделе [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md).  Когда пользователь добавляет элемент проекта настраиваемого действия в проект SharePoint мастер собирает сведения о настраиваемом действии \(например, его расположение и URL\-адрес для перехода, когда пользователь выбирает в нем\), и добавляет эти данные в файл Elements.xml нового элемента проекта.  
  
 В этом пошаговом руководстве показано выполнение следующих задач.  
  
-   Создание мастера для настраиваемого типа элемента проекта SharePoint, связанного с шаблоном элемента.  
  
-   Определение пользовательского интерфейса мастера, похожий на встроенных пользовательских мастеров для элементов проекта SharePoint в Visual Studio.  
  
-   Использование подстановочных параметров для инициализации файлов проекта SharePoint с данными, собранными мастером.  
  
-   Отладка и тестирование мастера.  
  
> [!NOTE]  
>  Можно загрузить образец, содержащая завершенные проекты, код и другие файлы для этого пошагового руководства из следующих расположений: [Файлы проекта для SharePoint оборудуют примеры расширяемости](http://go.microsoft.com/fwlink/?LinkId=191369).  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства необходимо в первую очередь создать решение CustomActionProjectItem, выполнив [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md).  
  
 Также для выполнения данного пошагового руководства на компьютере разработчика должны быть установлены следующие компоненты.  
  
-   Поддерживаемые выпуски Windows, SharePoint и Visual Studio.  Дополнительные сведения см. в разделе [Требования по разработке решений SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Пакет SDK для Visual Studio.  В этом пошаговом руководстве шаблон **Проект VSIX** из пакета SDK используется для создания пакета VSIX, который служит для развертывания элемента проекта.  Дополнительные сведения см. в разделе [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
 Знание следующих подходов может оказаться полезным, но не требуется для выполнения пошагового руководства.  
  
-   Мастера для проектов и шаблонов элементов в Visual Studio.  Дополнительные сведения см. в разделе [Практическое руководство. Использование мастеров для шаблонов проекта](~/extensibility/how-to-use-wizards-with-project-templates.md) и в документации на интерфейс <xref:Microsoft.VisualStudio.TemplateWizard.IWizard>.  
  
-   настраиваемые действия в SharePoint.  Дополнительные сведения см. в разделе [Custom Action](http://go.microsoft.com/fwlink/?LinkId=177800).  
  
## Создание проекта мастера  
 Для выполнения инструкций данного пошагового руководства необходимо добавить к решению проект CustomActionProjectItem, созданного в [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md).  Необходимо будет реализовать интерфейс <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> и определить пользовательский интерфейс мастера в этом проекте.  
  
#### Создание проекта мастера  
  
1.  В Visual Studio открытие решения CustomActionProjectItem  
  
2.  В **Обозреватель решений** открыть контекстное меню для узла решения выберите **Добавить**, а затем выберите **Создать проект**.  
  
    > [!NOTE]  
    >  В проектах Visual Basic узел решения отображается в **обозревателе решений**, только если в диалоговом окне ["Общие", страница "Проекты и решения", диалоговое окно "Параметры"](http://msdn.microsoft.com/ru-ru/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca) установлен флажок **Всегда показывать решение**.  
  
3.  В диалоговом окне **Создать проект** разверните узлы **Visual C\#** или **Visual Basic**, а затем выберите узел **Окна**.  
  
4.  В верхней части диалогового окна **Создать проект**, убедитесь, что **платформа .NET Framework 4,5** выбратьо в списке версий платформы .NET Framework.  
  
5.  Выберите шаблон проекта **Библиотека пользовательских элементов управления WPF**, назовите проект **ItemTemplateWizard**, а затем нажмите кнопку **ОК**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] добавит в решение проект **ItemTemplateWizard**.  
  
6.  Удалите элемент UserControl1 из проекта.  
  
## Настройка проекта мастера  
 Перед созданием мастер, необходимо добавить окно Windows Presentation Foundation \(WPF\), файл кода и ссылки на сборку в проект.  
  
#### Настройка проекта мастера  
  
1.  В **Обозреватель решений** открыть контекстное меню с узла проекта **ItemTemplateWizard**, а затем выберите **Свойства**.  
  
2.  В **Конструктор проектов** проверьте, что требуемая версия .NET Framework устанавливаются на платформу .NET Framework 4,5.  
  
     Для проектов visual C\#, можно установить это значение на вкладке **Приложение**.  Для проектов Visual Basic, можно установить это значение на вкладке **Компилировать**.  Дополнительные сведения см. в разделе [Практическое руководство. Определение целевой версии .NET Framework](~/ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
3.  В проекте **ItemTemplateWizard** добавьте элемент **Окно \(WPF\)** в проект и назовите элемент **WizardWindow**.  
  
4.  Добавьте 2 файла кода, называются CustomActionWizard и строками.  
  
5.  Открыть контекстное меню для проекта **ItemTemplateWizard**, а затем выберите **Добавить ссылку**.  
  
6.  В диалоговом окне **Диспетчер ссылок \- ItemTemplateWizard** под узлом **Сборки** выберите узел **Расширения**.  
  
7.  Установите флажки рядом с следующими сборками, а затем нажмите кнопку **ОК**:  
  
    -   EnvDTE  
  
    -   Microsoft.VisualStudio.Shell.11.0  
  
    -   Microsoft.VisualStudio.TemplateWizardInterface  
  
8.  В **Обозреватель решений** в папке **Ссылки** для проекта ItemTemplateWizard выберите ссылку **EnvDTE**.  
  
    > [!NOTE]  
    >  В проектах Visual Basic папка **Ссылки** отображается, только если в окне ["Общие", страница "Проекты и решения", диалоговое окно "Параметры"](http://msdn.microsoft.com/ru-ru/8f8e37e8-b28d-4b13-bfeb-ea4d3312aeca) установлен флажок **Всегда показывать решение**.  
  
9. В окне **Свойства** измените значение свойства **Внедрить типы взаимодействия** к **Ложь**.  
  
## Определение строк "Расположение по умолчанию" и "ID" для настраиваемых действий  
 У любого настраиваемого действия есть расположение и идентификатор, заданные атрибутами `GroupID` и `Location` элемента `CustomAction` в файле Elements.xml.  На этом этапе необходимо задать допустимые значения для данных атрибутов в проекте ItemTemplateWizard.  При изучении в этом пошаговом руководстве эти строки записаны в файл Elements.xml в элементе проекта настраиваемого действия, когда пользователи задают расположение и идентификатор в мастере.  
  
 Для простоты данный пример описывает лишь подмножество доступных по умолчанию расположений и идентификаторов.  Полный список см. в разделе [Default Custom Action Locations and IDs](http://go.microsoft.com/fwlink/?LinkId=181964).  
  
#### Определение строк по умолчанию, содержащих расположение и идентификатор  
  
1.  открыть.  
  
2.  В проекте **ItemTemplateWizard** замените код в файле кода строк со следующим кодом.  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#6](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/cs/itemtemplatewizard/strings.cs#6)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#6](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/vb/itemtemplatewizard/strings.vb#6)]  
  
## Создание пользовательского интерфейса мастера  
 Добавьте XAML, чтобы определить пользовательский интерфейс мастера, и добавьте код привязки некоторых элементов управления в мастере к строкам идентификаторов.  Мастер, который будет создан похожий на встроенный мастер проектов SharePoint в Visual Studio.  
  
#### Создание пользовательского интерфейса мастера  
  
1.  В проекте **ItemTemplateWizard** открыть контекстное меню для файла **WizardWindow.xaml**, а затем выберите **Открыть** чтобы открыть окно в конструкторе.  
  
2.  В представлении XAML, замените текущий язык XAML следующим кодом XAML.  Этот код XAML определяет пользовательский интерфейс, содержащий заголовок, элементы управления для указания поведения настраиваемого действия и кнопки навигации в нижней части окна.  
  
    > [!NOTE]  
    >  Проект будет иметь некоторые компилировать ошибки после добавления этого кода.  Эти ошибки исчезнут при добавлении кода на следующих шагах.  
  
     [!code-xml[SPExtensibility.ProjectItem.CustomAction#9](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/cs/itemtemplatewizard/wizardwindow.xaml#9)]  
  
    > [!NOTE]  
    >  Окно, создано в данном языке XAML является производным от базового класса <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>.  При добавлении пользовательское диалоговое окно WPF в Visual Studio рекомендуется наследовать диалоговое окно от этого класса, чтобы иметь согласованный styling с другими диалоговыми окнами в Visual Studio и избежать проблем, которые могут возникать в противном случае с окнами модальным диалогового окна.  Дополнительные сведения см. в разделе [Создание и управление модальные диалоговые окна](../extensibility/creating-and-managing-modal-dialog-boxes.md).  
  
3.  Если разрабатываемый проект Visual Basic, удалите пространство имен `ItemTemplateWizard` от имени класса `WizardWindow` в атрибуте `x:Class` элемента `Window`.  Этот элемент первой линии XAML.  По завершении, первая линия должна выглядеть следующим образом:  
  
    ```  
    <Window x:Class="WizardWindow"  
    ```  
  
4.  В файле с выделенным кодом для файла WizardWindow.xaml замените текущий код следующим кодом.  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#7](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/cs/itemtemplatewizard/wizardwindow.xaml.cs#7)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#7](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/vb/itemtemplatewizard/wizardwindow.xaml.vb#7)]  
  
## Реализация мастера  
 Определите функциональность мастера, реализовав интерфейс <xref:Microsoft.VisualStudio.TemplateWizard.IWizard>.  
  
#### Реализация мастера  
  
1.  В проекте **ItemTemplateWizard**, откройте файл кода **CustomActionWizard**, а затем заменить текущий код в этом файле следующим кодом:  
  
     [!code-csharp[SPExtensibility.ProjectItem.CustomAction#8](../snippets/csharp/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/cs/itemtemplatewizard/customactionwizard.cs#8)]
     [!code-vb[SPExtensibility.ProjectItem.CustomAction#8](../snippets/visualbasic/VS_Snippets_OfficeSP/spextensibility.projectitem.customaction/vb/itemtemplatewizard/customactionwizard.vb#8)]  
  
## Контрольная точка  
 На данном этапе выполнения пошагового руководства проект содержит весь код, необходимый для реализации мастера.  Выполните построение проекта, чтобы убедиться, что компиляция выполняется без ошибок.  
  
#### Построение проекта  
  
1.  В строке меню выберите **Построение**, **Построить решение**.  
  
## Привязка мастера к шаблону элемента  
 Теперь, когда реализован мастер, необходимо связать его с шаблоном элемента, выполнив **Настраиваемое действие** 3 основных этапов:  
  
1.  подпишите сборку мастера строгим именем;  
  
2.  получите токен открытого ключа для сборки мастера;  
  
3.  добавьте ссылку в сборку мастера в VSTEMPLATE\-файле для шаблона элемента **Настраиваемое действие**.  
  
#### Подписывание сборки мастера строгим именем  
  
1.  В **Обозреватель решений** открыть контекстное меню с узла проекта **ItemTemplateWizard**, а затем выберите **Свойства**.  
  
2.  На вкладке **Подписи** установите флажок **Подписать сборку**.  
  
3.  В списке выберите **\<New...\>Выберите файл ключа строгого имени**.  
  
4.  В диалоговом окне **Создание ключа строгого имени** введите имя, снимите флажок **Защитить мой файл ключей паролем**, а затем нажмите кнопку **ОК**.  
  
5.  В строке меню выберите **Построение**, **Построить решение**.  
  
#### Получение токена открытого ключа для сборки мастера  
  
1.  В окне командной строки Visual Studio выполните следующую команду, заменив *PathToWizardAssembly* полным путем к построенной сборке ItemTemplateWizard.dll для проекта ItemTemplateWizard на компьютере разработчика.  
  
    ```  
    sn.exe -T PathToWizardAssembly  
    ```  
  
     Токен открытого ключа для сборки ItemTemplateWizard.dll выводится в окне командной строки Visual Studio.  
  
2.  Не закрывайте окно командной строки Visual Studio.  Токен открытого ключа, необходимо выполнить следующую процедуру.  
  
#### Добавление ссылки на сборку мастера в VSTEMPLATE\-файл  
  
1.  В **Обозреватель решений** разверните узел проекта **ItemTemplate**, а затем откройте файл ItemTemplate.vstemplate.  
  
2.  Добавьте следующий элемент `WizardExtension` между тегами `</TemplateContent>` и `</VSTemplate>` \(ближе к концу файла\).  Замените значение *YourToken* атрибута `PublicKeyToken` с токеном открытого ключа, которые получили в предыдущей процедуре.  
  
    ```  
    <WizardExtension>  
      <Assembly>ItemTemplateWizard, Version=1.0.0.0, Culture=neutral, PublicKeyToken=YourToken</Assembly>  
      <FullClassName>ItemTemplateWizard.CustomActionWizard</FullClassName>  
    </WizardExtension>  
    ```  
  
     Дополнительные сведения об элементе `WizardExtension` см. в разделе [Элемент WizardExtension &#40;шаблоны Visual Studio&#41;](../extensibility/wizardextension-element-visual-studio-templates.md).  
  
3.  Сохраните и закройте файл.  
  
## Добавление подстановочных параметров в файл Elements.xml шаблона элемента  
 Добавьте несколько подстановочных параметров в файл Elements.xml проекта ItemTemplate.  Эти параметры инициализируются методом `PopulateReplacementDictionary` класса `CustomActionWizard`, определенного ранее.  При добавлении пользователем в проект элемента проекта "Настраиваемое действие" Visual Studio автоматически заменяет эти параметры в файле Elements.xml нового элемента проекта значениями, указанными пользователем в мастере.  
  
 Меняемый параметр токен, который начинается и заканчивается знаком доллара \($\).  Помимо указания собственных подстановочные параметры можно использовать встроенные параметры, что система проекта SharePoint определяет и выполняет инициализацию.  Дополнительные сведения см. в разделе [Подстановочные параметры](../sharepoint/replaceable-parameters.md).  
  
#### Добавление подстановочных параметров в файл Elements.xml  
  
1.  В проект ItemTemplate замените содержимое файла Elements.xml следующим XML\-кодом.  
  
    ```  
  
    <Elements Id="$guid8$" xmlns="http://schemas.microsoft.com/sharepoint/">  
      <CustomAction Id="$IdValue$"  
                    GroupId="$GroupIdValue$"  
                    Location="$LocationValue$"  
                    Sequence="1000"  
                    Title="$TitleValue$"  
                    Description="$DescriptionValue$" >  
        <UrlAction Url="$UrlValue$"/>  
      </CustomAction>  
    </Elements>  
    ```  
  
     Новый XML\-код изменит значения атрибутов `Id`, `GroupId`, `Location`, `Description` и `Url` на подстановочные параметры.  
  
2.  Сохраните и закройте файл.  
  
## Добавление мастера в пакет VSIX  
 В файле source.extension.vsixmanifest в проекте VSIX добавьте ссылку на проект мастера, чтобы он развертывался в пакете VSIX, содержащую элемент проекта.  
  
#### Добавление мастера в пакет VSIX  
  
1.  В **Обозреватель решений** открыть контекстное меню **source.extension.vsixmanifest** из файла в проект CustomActionProjectItem, а затем выберите **Открыть**, чтобы открыть файл в редакторе манифестов.  
  
2.  В редакторе манифестов, выберите вкладку **Активы**, а затем нажмите кнопку **Создать**.  
  
     Диалоговое окно **Добавить новый актив**.  
  
3.  В списке **Тип** выберите **Microsoft.VisualStudio.Assembly**.  
  
4.  В списке **Источник** выберите **Проект в текущем решении**.  
  
5.  В списке **Проект** выберите **ItemTemplateWizard**, а затем нажмите кнопку **ОК**.  
  
6.  В строке меню выберите **Построение**, **Построить решение** и убедитесь, что решение будет компилироваться без ошибок.  
  
## Тестирование мастера  
 Мастер готов к тестированию.  Во\-первых, начните отладку решения CustomActionProjectItem в экспериментальном экземпляре Visual Studio.  Затем проверьте мастер для элемента проекта настраиваемого действия в проекте SharePoint в экспериментальном экземпляре Visual Studio.  И наконец, выполните построение и запустите проект SharePoint, чтобы проверить, что настраиваемое действие работает ожидаемым образом.  
  
#### Начать отладку решения  
  
1.  Перезапустите Visual Studio с учетными данными администратора, а затем открыть решения CustomActionProjectItem.  
  
2.  В проекте ItemTemplateWizard, откройте файл кода CustomActionWizard, а затем добавьте точку останова на первой строке кода в методе `RunStarted`.  
  
3.  В строке меню выберите **Отладка**, **Исключения**.  
  
4.  В диалоговом окне **Исключения**, убедитесь, что очищены флажки **Вызванное** и **Не обработанное пользовательским кодом** для **Исключения среды CLR**, а затем выбрать кнопку **ОК**.  
  
5.  Начать отладку путем выбора ключа F5 либо в строке меню, при выборе **Отладка**, **Начать отладку**.  
  
     Visual Studio устанавливает расширения до %UserProfile% \\ AppData \\ local \\ Microsoft \\ VisualStudio \\ 11.0Exp \\ extensions \\ Contoso \\ элемент проекта настраиваемого действия \\ 1.0 и запускает экспериментальном экземпляре Visual Studio.  Тестировании элемент проекта в данном экземпляре Visual Studio.  
  
#### Тестирование мастера в Visual Studio  
  
1.  В экспериментальном экземпляре Visual Studio в строке меню выберите **Файл**, **Создать**, **Проект**.  
  
2.  Разверните узел **Visual C\#** или **Visual Basic** \(в зависимости от языка, который поддерживает шаблон элемента\) разверните узел **SharePoint**, а затем выберите узел **2010**.  
  
3.  В списке шаблонов проектов выберите **Проект SharePoint 2010**, назовите проект **CustomActionWizardTest**, а затем нажмите кнопку **ОК**.  
  
4.  В **Мастер настройки SharePoint** введите URL\-адрес сайта, который необходимо использовать для отладки, а затем нажмите кнопку **Готово**.  
  
5.  В **Обозреватель решений** открыть контекстное меню для узла проекта выберите **Добавить**, а затем выберите **Создать элемент**.  
  
6.  В диалоговом окне **добавьте новый элемент \- CustomItemWizardTest** разверните узел **SharePoint**, а затем разверните узел **2010**.  
  
7.  В списке элементов проекта выберите элемент **Настраиваемое действие**, а затем нажмите кнопку **Добавить**.  
  
8.  Убедитесь, что выполнение кода в другом экземпляре Visual Studio прерывается на точке останова, заданной ранее в методе `RunStarted`.  
  
9. Чтобы продолжить отладку проекта, выбрав ключ F5 либо в строке меню, при выборе **Отладка**, **Продолжить**.  
  
     Появится окно "Мастер настройки SharePoint".  
  
10. В **Расположение** выберите переключатель **правка списка**.  
  
11. В списке **Идентификатор группы** выберите **Связь**.  
  
12. В окне **Название** введите **Центр разработчика SharePoint**.  
  
13. В окне **Описание** введите **Открывает веб\-сайт центра разработчиков SharePoint**.  
  
14. В окне **URL\-адрес**, вставки **http:\/\/msdn.microsoft.com\/sharepoint\/default.aspx**, а затем кнопку **Готово**.  
  
     isual studio добавляет элемент с именем **CustomAction1** в проект и открывается файл Elements.xml в редакторе.  Проверьте, что в файле Elements.xml содержатся значения, заданные в мастере.  
  
#### Тестирование настраиваемого действия в SharePoint  
  
1.  В экспериментальном экземпляре Visual Studio выберите ключ F5 либо в строке меню выберите **Отладка**, **Начать отладку**.  
  
     Пользовательское действие было представлено отдельным пакетом, пригодным к сайту SharePoint и развертыватьо, определенное свойством **URL\-адрес сайта** проекта и Интернет\-браузер открывает страницу по умолчанию данного сайта.  
  
    > [!NOTE]  
    >  Если откроется диалоговое окно **Отладка скриптов отключена** отображается, нажмите кнопку **Да**.  
  
2.  В области списков сайта SharePoint выберите ссылку **Задачи**.  
  
     Страница **задачи – все задачи**.  
  
3.  На вкладке ленты **Инструменты списка** выберите вкладку **Список**, а затем в группе **Параметры** выберите **параметры списка**.  
  
     Страница **Перечисляет параметры**.  
  
4.  В **Связь** заголовок в верхней части страницы выберите ссылку **Центр разработчика SharePoint**, убедитесь, что браузер открывает веб\-сайт http:\/\/msdn.microsoft.com\/sharepoint\/default.aspx, а затем закройте браузер.  
  
## Очистка компьютера разработчика  
 После завершения тестирования элемента проекта удалите шаблон элемента проекта из экспериментального экземпляра Visual Studio.  
  
#### Очистка компьютера разработчика  
  
1.  В экспериментальном экземпляре Visual Studio в строке меню выберите **Сервис**, **Расширения и обновления**.  
  
     Будет открыто диалоговое окно **Расширения и обновления**.  
  
2.  В списке расширений выберите расширение **элемент проекта настраиваемого действия**, а затем нажмите кнопку **Удалить**.  
  
3.  В появившемся диалоговом окне нажмите кнопку **Да**, чтобы подтвердить удаление расширения, а затем нажмите кнопку **Перезагрузить сейчас** для завершения удаления.  
  
4.  Закройте оба экземпляра Visual Studio \(экспериментальном экземпляра и экземпляр Visual Studio, в котором решения CustomActionProjectItem открыто\).  
  
## См. также  
 [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [Defining Custom SharePoint Project Item Types](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Creating Item Templates and Project Templates for SharePoint Project Items](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Справочник по схеме шаблонов Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Практическое руководство. Использование мастеров для шаблонов проекта](~/extensibility/how-to-use-wizards-with-project-templates.md)   
 [По умолчанию расположений и идентификаторы настраиваемых действий](http://go.microsoft.com/fwlink/?LinkId=181964)  
  
  