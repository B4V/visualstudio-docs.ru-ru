---
title: 'Пошаговое руководство: Расширение типа элемента проекта SharePoint | Документация Майкрософт'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e1210d95a73038ea21c0455e944eb46b1791b426
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49844520"
---
# <a name="walkthrough-extend-a-sharepoint-project-item-type"></a>Пошаговое руководство: Расширение типа элемента проекта SharePoint
  Можно использовать **Business Data Connectivity Model** элемент проекта для создания модели для службы бизнес-данным (BDC) в SharePoint. По умолчанию при создании модели с помощью этого элемента проекта, данные в модели не отображается для пользователей. Также необходимо создать внешний список в SharePoint, чтобы пользователи могли просматривать данные.  
  
 В этом пошаговом руководстве вы создадите расширения **Business Data Connectivity Model** элемент проекта. Разработчики могут использовать расширения для создания внешнего списка в своих проектах, в котором данные будут отображены в модели BDC. В этом пошаговом руководстве описаны следующие задачи.  
  
-   Создание расширения Visual Studio, который выполняет две основные задачи:  
  
    -   Он создает внешний список, отображающий данные в модели BDC. Расширение использует объектную модель для системы проектов SharePoint для создания *Elements.xml* файл, определяющий список. Он также добавляет файл в проект таким образом, чтобы оно развертывается вместе с моделью BDC.  
  
    -   Он добавляет пункта контекстного меню к **Business Data Connectivity Model** элементами проекта в среде **обозревателе решений**. Разработчикам можно щелкнуть этот элемент меню, чтобы создать внешний список для модели BDC.  
  
-   Построение пакета Visual Studio Extension (VSIX) развертывание сборки модуля.  
  
-   Тестирование расширения.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Необходимы следующие компоненты на компьютере разработчика для выполнения этого пошагового руководства.  
  
- Поддерживаемые выпуски Visual Studio, SharePoint и Microsoft Windows.  
  
- [!include[vssdk_current_long](../sharepoint/includes/vssdk-current-long-md.md)]. В этом пошаговом руководстве использует **проект VSIX** шаблона в пакете SDK для создания пакета VSIX для развертывания элемента проекта. Дополнительные сведения см. в разделе [расширения инструментов SharePoint в Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md).  
  
  Знание следующие основные понятия будут полезны, но не требуется для выполнения данного пошагового руководства:  
  
- Служба BDC в [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]. Дополнительные сведения см. в разделе [архитектура BDC](http://go.microsoft.com/fwlink/?LinkId=177798).  
  
- Схема XML для модели BDC. Дополнительные сведения см. в разделе [инфраструктуре модели BDC](http://go.microsoft.com/fwlink/?LinkId=177799).  
  
## <a name="create-the-projects"></a>Создание проектов
 Для выполнения этого пошагового руководства, необходимо создать два проекта:  
  
- Проект VSIX, чтобы создать пакет VSIX для развертывания расширения элемента проекта.  
  
- Проект библиотеки классов, реализующий расширение элемента проекта.  
  
  Начало выполнения пошагового руководства по созданию проектов.  
  
#### <a name="to-create-the-vsix-project"></a>Создание проекта VSIX  
  
1.  Запустите [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  В строке меню выберите **Файл** > **Создать** > **Проект**.  
  
3.  В **новый проект** диалогового окна разверните узел **Visual C#** или **Visual Basic** узлов и нажмите кнопку **расширяемости** узла.  
  
    > [!NOTE]  
    >  **Расширяемости** узел доступен только в том случае, если установить пакет SDK для Visual Studio. Дополнительные сведения см. в разделе "Предварительные требования" ранее в этом разделе.  
  
4.  В списке в верхней части **новый проект** диалоговом окне выберите **.NET Framework 4.5**.  
  
     Расширения инструментов SharePoint требуют возможности в этой версии платформы .NET Framework.  
  
5.  Выберите **проект VSIX** шаблона.  
  
6.  В **имя** введите **GenerateExternalDataLists**, а затем выберите **ОК** кнопки.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Добавляет **GenerateExternalDataLists** проект **обозревателе решений**.  
  
7.  Если файл source.extension.vsixmanifest не запустился, откройте его контекстное меню в проекте GenerateExternalDataLists и выберите **откройте**  
  
8.  Убедитесь, что файл source.extension.vsixmanifest запись непустой (введите Contoso) для поля "Автор", сохраните файл и закройте его.  
  
#### <a name="to-create-the-extension-project"></a>Создание проекта расширения  
  
1.  В **обозревателе решений**, откройте контекстное меню для **GenerateExternalDataLists** узел решения, выберите **добавить**, а затем выберите **новый проект**.  
  
2.  В **Добавление нового проекта** диалоговое окно последовательно раскройте элементы **Visual C#** или **Visual Basic** узлов, а затем выберите **Windows** узел.  
  
3.  В списке в верхней части диалогового окна выберите **.NET Framework 4.5**.  
  
4.  В списке шаблонов проектов выберите **библиотеки классов**.  
  
5.  В **имя** введите **BdcProjectItemExtension**, а затем выберите **ОК** кнопки.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Добавляет **BdcProjectItemExtension** проекта в решение и открывает файл кода по умолчанию Class1.  
  
6.  Удалите файл Class1 код из проекта.  
  
## <a name="configure-the-extension-project"></a>Настройка проекта расширения
 Прежде чем писать код для создания расширения элемента проекта, добавьте файлы кода и ссылки на сборки в проект расширения.  
  
#### <a name="to-configure-the-project"></a>Настройка проекта  
  
1.  В проекте BdcProjectItemExtension добавьте два файла кода, которые имеют следующие имена:  
  
    -   ProjectItemExtension  
  
    -   GenerateExternalDataLists  
  
2.  Выберите проект BdcProjectItemExtension, а затем в строке меню выберите **проекта** > **добавить ссылку**.  
  
3.  В разделе **сборки** узел, выберите **Framework** узла и установите флажок для каждого из следующих сборок:  
  
    -   System.ComponentModel.Composition  
  
    -   WindowsBase  
  
4.  В разделе **сборки** узел, выберите **расширения** узел, а затем выберите флажок для следующей сборки:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
5.  Нажмите кнопку **ОК** .  
  
## <a name="define-the-project-item-extension"></a>Определение расширения элемента проекта
 Создайте класс, который определяет расширение **Business Data Connectivity Model** элемент проекта. Чтобы определить расширение, этот класс реализует <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> интерфейс. Реализуйте этот интерфейс, каждый раз, когда вы хотите расширить существующий тип элемента проекта.  
  
#### <a name="to-define-the-project-item-extension"></a>Для определения расширения элемента проекта  
  
1.  Вставьте следующий код в файле кода ProjectItemExtension.  
  
    > [!NOTE]  
    >  После добавления этого кода, проект будет содержать некоторые ошибки компиляции. Эти ошибки исчезнут при добавлении кода в последующих шагах.  
  
     [!code-csharp[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#1](../sharepoint/codesnippet/CSharp/generateexternaldatalists/bdcprojectitemextension/projectitemextension.cs#1)]
     [!code-vb[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#1](../sharepoint/codesnippet/VisualBasic/generateexternaldatalists/bdcprojectitemextension/projectitemextension.vb#1)]  
  
## <a name="create-the-external-data-lists"></a>Создание внешних списков данных
 Добавьте частичное определение `GenerateExternalDataListsExtension` класс, который создает внешний список данных для каждой сущности в модели BDC. Чтобы создать список внешних данных, этот код сначала считывает данные сущности в модели BDC путем синтаксического анализа XML-данные в файле модели. Затем он создает экземпляр списка, который основан на модели BDC и добавляет этот экземпляр списка в проект.  
  
#### <a name="to-create-the-external-data-lists"></a>Для создания списков внешних данных  
  
1.  Вставьте следующий код в файле кода GenerateExternalDataLists.  
  
     [!code-vb[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#2](../sharepoint/codesnippet/VisualBasic/generateexternaldatalists/bdcprojectitemextension/generateexternaldatalists.vb#2)]
     [!code-csharp[SPExtensibility.ProjectItemExtension.BDCGenerateExternalDataLists#2](../sharepoint/codesnippet/CSharp/generateexternaldatalists/bdcprojectitemextension/generateexternaldatalists.cs#2)]  
  
## <a name="checkpoint"></a>Контрольная точка  
 На этом этапе в этом пошаговом руководстве, весь код для расширения элемента проекта находится в проект. Постройте решение, чтобы убедиться, что проект компилируется без ошибок.  
  
#### <a name="to-build-the-solution"></a>Построение решения  
  
1.  В строке меню последовательно выберите **Сборка**  >  **Собрать решение**.  
  
## <a name="create-a-vsix-package-to-deploy-the-project-item-extension"></a>Создание пакета VSIX для развертывания расширения элемента проекта
 Чтобы развернуть расширение, используйте проекта VSIX в решении для создания пакета VSIX. Во-первых настройте пакет VSIX, изменив файл source.extension.vsixmanifest, включенный в проект VSIX. Затем создайте пакет VSIX, построения решения.  
  
#### <a name="to-configure-and-create-the-vsix-package"></a>Настройка и создание пакета VSIX  
  
1.  В **обозревателе решений**, откройте контекстное меню для файла source.extension.vsixmanifest в проекте GenerateExternalDataLists и затем выберите **откройте**.  
  
     Visual Studio открывает файл в редакторе манифестов. Файл source.extension.vsixmanifest — это основа для файл extension.vsixmanifest необходим для всех пакетов VSIX. Дополнительные сведения об этом файле см. в разделе [Справочник по схеме 1.0 VSIX расширения](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b).  
  
2.  В **название продукта** введите **генератор внешнего списка данных**.  
  
3.  В **автор** введите **Contoso**.  
  
4.  В **описание** введите **расширения элемента проекта Business Data Connectivity Model, которые позволяют создавать внешние списки данных**.  
  
5.  На **активы** вкладка редактора выберите **New** кнопки.  
  
     **Добавить новый актив** откроется диалоговое окно.  
  
6.  В **тип** выберите **Microsoft.VisualStudio.MefComponent**.  
  
    > [!NOTE]  
    >  Это значение соответствует `MefComponent` элемент в файл extension.vsixmanifest. Этот элемент задает имя сборки расширения в пакете VSIX. Дополнительные сведения см. в разделе [MEFComponent элемент (Схема VSX)](http://msdn.microsoft.com/en-us/8a813141-8b73-44c9-b80b-ca85bbac9551).  
  
7.  В **источника** выберите **проект в текущем решении**.  
  
8.  В **проекта** выберите **BdcProjectItemExtension**, а затем выберите **ОК** кнопки.  
  
9. В строке меню последовательно выберите **Сборка**  >  **Собрать решение**.  
  
10. Убедитесь, что проект компилируется и сборка выполняется без ошибок.  
  
11. Убедитесь, что в выходную папку построения для проекта GenerateExternalDataLists теперь содержит файл GenerateExternalDataLists.vsix.  
  
     По умолчанию является выходной папке сборки... папку \bin\debug в папке, содержащей файл проекта.  
  
## <a name="test-the-project-item-extension"></a>Тестирование расширения элемента проекта
 Теперь вы готовы к тестированию расширения элемента проекта. Начните отладку проекта расширения в экспериментальном экземпляре Visual Studio. Затем используйте расширения в экспериментальном экземпляре Visual Studio, чтобы создать внешний список для модели BDC. Наконец откройте внешний список на сайте SharePoint, чтобы убедиться, что оно работает должным образом.  
  
#### <a name="to-start-debugging-the-extension"></a>Чтобы начать отладку расширения  
  
1.  При необходимости перезапустите Visual Studio от имени администратора и откройте решение GenerateExternalDataLists.  
  
2.  В проекте BdcProjectItemExtension, откройте файл кода ProjectItemExtension и затем добавьте точку останова в строку кода в `Initialize` метод.  
  
3.  Откройте файл кода GenerateExternalDataLists и затем добавьте точку останова в первой строке кода в `GenerateExternalDataLists_Execute` метод.  
  
4.  Начать отладку, выбрав **F5** ключа или в строке меню выберите **Отладка** > **начать отладку**.  
  
     Visual Studio устанавливает расширение для %UserProfile%\AppData\Local\Microsoft\VisualStudio\10.0Exp\Extensions\Contoso\External Generator\1.0 список данных и запускает экспериментальный экземпляр Visual Studio. Элемент проекта будут тестироваться в этот экземпляр Visual Studio.  
  
#### <a name="to-test-the-extension"></a>Чтобы проверить расширение  
  
1.  В экспериментальном экземпляре Visual Studio в строке меню выберите **файл** > **New** > **проекта**.  
  
2.  В **новый проект** диалоговое окно последовательно раскройте элементы **шаблоны** узел, разверните **Visual C#** узел, разверните **SharePoint** узел, а затем Выберите **2010**.  
  
3.  Убедитесь, что в списке в верхней части диалогового окна, **.NET Framework 3.5** выбран. Проекты для [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] требуется этой версии платформы .NET Framework.  
  
4.  В списке шаблонов проектов выберите **проект SharePoint 2010**.  
  
5.  В **имя** введите **SharePointProjectTestBDC**, а затем выберите **ОК** кнопки.  
  
6.  В мастере настройки SharePoint, введите URL-адрес сайта, который вы хотите использовать для отладки, выберите **развернуть как решение фермы**, а затем выберите **Готово**кнопки.  
  
7.  Откройте контекстное меню для проекта SharePointProjectTestBDC, выберите **добавить**, а затем выберите **новый элемент**.  
  
8.  В **добавьте NewItem - SharePointProjectTestBDC** диалогового окна разверните узел установленный язык последовательно раскройте элементы **SharePoint** узла.  
  
9. Выберите **2010** узел, а затем выберите **Business Data Connectivity Model (только для решения фермы)** шаблона.  
  
10. В **имя** введите **TestBDCModel**, а затем выберите **добавить** кнопки.  
  
11. Убедитесь, что выполнение кода в другом экземпляре Visual Studio будет приостановлено в точке останова, заданные в `Initialize` метод ProjectItemExtension файла кода.  
  
12. В остановленной экземпляре Visual Studio, выберите **F5** ключа, либо в строке меню выберите **Отладка** > **Продолжить** продолжить отладку проекта.  
  
13. В экспериментальном экземпляре Visual Studio, выберите **F5** ключа или в строке меню выберите **Отладка** > **начать отладку** для построения, развертывания и запуска **TestBDCModel** проекта.  
  
     Веб-браузер открывает страницу по умолчанию для сайта SharePoint, которая указана для отладки.  
  
14. Убедитесь, что **перечислены** раздел в области быстрого запуска еще не содержит список, основанный на модели BDC по умолчанию в проекте. Во-первых, необходимо создать внешний список данных, либо с помощью пользовательского интерфейса SharePoint, либо с помощью расширения элемента проекта.  
  
15. Закройте веб-браузер.  
  
16. В экземпляре Visual Studio с TestBDCModel открывает проект, откройте контекстное меню для **TestBDCModel** узел в **обозревателе решений**, а затем выберите **создания внешних данных Список**.  
  
17. Убедитесь, что выполнение кода в другом экземпляре Visual Studio будет приостановлено в точке останова, заданные в `GenerateExternalDataLists_Execute` метод. Выберите **F5** ключа или в строке меню выберите **Отладка** > **Продолжить** продолжить отладку проекта.  
  
18. Экспериментальный экземпляр Visual Studio добавляет экземпляр списка, который называется **Entity1DataList** TestBDCModel проекта, а экземпляр также создает функцию, которая называется **компонент2** для списка экземпляр.  
  
19. Выберите **F5** ключа или в строке меню выберите **Отладка** > **начать отладку** для построения, развертывания и запуска проекта TestBDCModel.  
  
     Веб-браузер открывает страницу по умолчанию для сайта SharePoint, который используется для отладки.  
  
20. В **перечислены** раздел на панели быстрого запуска выберите **Entity1DataList** списка.  
  
21. Убедитесь, что список содержит столбцы с именами идентификатор1 и сообщения, а также один элемент, который имеет значение "идентификатор1" 0 "и" значение "сообщение" Hello World.  
  
     **Business Data Connectivity Model** шаблон проекта создает модели BDC по умолчанию, которая предоставляет все эти данные.  
  
22. Закройте веб-браузер.  
  
## <a name="clean-up-the-development-computer"></a>Очистка компьютера разработчика
 После завершения тестирования расширения элемента проекта, удалить внешний список и модель BDC с сайта SharePoint и удалите расширение элемента проекта из Visual Studio.  
  
#### <a name="to-remove-the-external-data-list-from-the-sharepoint-site"></a>Чтобы удалить список внешних данных с сайта SharePoint  
  
1.  В области быстрого запуска на сайте SharePoint выберите **Entity1DataList** списка.  
  
2.  На ленте на сайте SharePoint, выберите **списка** вкладки.  
  
3.  На **списка** на вкладке **параметры** группе, выберите **параметры списка**.  
  
4.  В разделе **разрешения и управление**, выберите **удалить этот список**, а затем выберите **ОК** для подтверждения того, что вы хотите отправить список в корзину.  
  
5.  Закройте веб-браузер.  
  
#### <a name="to-remove-the-bdc-model-from-the-sharepoint-site"></a>Чтобы удалить модель BDC с сайта SharePoint  
  
1.  В экспериментальном экземпляре Visual Studio в строке меню выберите **построения** > **Retract**.  
  
     Visual Studio удаляет модель BDC с сайта SharePoint.  
  
#### <a name="to-remove-the-project-item-extension-from-visual-studio"></a>Чтобы удалить расширение элемента проекта из Visual Studio  
  
1.  В экспериментальном экземпляре Visual Studio в строке меню выберите **средства** > **расширения и обновления**.  
  
     Появится диалоговое окно **Расширения и обновления**.  
  
2.  В списке расширений, выберите **генератор внешнего списка данных**, а затем выберите **удаления** кнопку.  
  
3.  В появившемся диалоговом окне, выберите **Да** для подтверждения того, что вы хотите удалить расширение.  
  
4.  Выберите **Перезагрузить сейчас** для завершения удаления.  
  
5.  Закройте оба экземпляра Visual Studio (экспериментальный экземпляр и экземпляр, в котором открыто решение GenerateExternalDataLists).  
  
## <a name="see-also"></a>См. также
 [Расширение системы проектов SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)   
 [Создание модели подключения к бизнес-данных](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [Проектирование модели подключения к бизнес-данным](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  
