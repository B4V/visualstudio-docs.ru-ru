---
title: "Изменение закодированных тестов пользовательского интерфейса с помощью редактора закодированных тестов пользовательского интерфейса | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codedUItest.testeditor
helpviewer_keywords:
- coded UI test, Coded UI Test Editor
ms.assetid: 76435c4b-593e-43a3-a9fe-709a7f9f5e0f
caps.latest.revision: 40
ms.author: douge
manager: douge
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: 55fd09e8c704152b1c88050adc567f28f37a7047
ms.contentlocale: ru-ru
ms.lasthandoff: 05/13/2017

---
# <a name="editing-coded-ui-tests-using-the-coded-ui-test-editor"></a>Изменение закодированных тестов пользовательского интерфейса с помощью редактора закодированных тестов пользовательского интерфейса
Редактор закодированных тестов пользовательского интерфейса позволяет легко изменять закодированные тесты пользовательского интерфейса. В редакторе закодированных тестов пользовательского интерфейса можно искать, просматривать и редактировать свойства методов теста и действия пользовательского интерфейса. Кроме того, можно использовать карту элементов управления пользовательского интерфейса для просмотра и редактирования соответствующих элементов управления.  
  
 **Требования**  
  
-   Visual Studio Enterprise  
  
## <a name="why-should-i-do-this"></a>Почему требуется сделать это?  
 Эффективнее и быстрее работать в редакторе закодированных тестов пользовательского интерфейса, чем редактировать код методов закодированных тестов пользовательского интерфейса в редакторе кода. В редакторе закодированных тестов пользовательского интерфейса можно использовать панель инструментов и контекстное меню для быстрого поиска, а также изменять значения свойств, связанных с действиями пользовательского интерфейса и элементами управления. Например, с помощью панели инструментов редактора закодированных тестов пользовательского интерфейса вы можете выполнить следующие команды.  
  
 ![Редактор тестов пользовательского интерфейса](~/test/media/uitesteditor.png "UITestEditor")  
  
1.  Команда [Найти](../ide/finding-and-replacing-text.md) позволяет определить расположение действий и элементов управления пользовательского интерфейса.  
  
2.  Команда[Удалить](#CodedUITestEditor_DeleteUIActions) удаляет ненужные действия пользовательского интерфейса.  
  
3.  Команда**Переименовать** изменяет имена методов и элементов управления теста.  
  
4.  Команда**Свойства** opens the Свойства Window for selected item.  
  
5.  Команда[Разделить и поместить в новый метод](#CodedUITestEditor_SplitMethods) позволяет разбить действия пользовательского интерфейса на модули.  
  
6.  Команда[Переместить код](#CodedUITestEditor_MoveMethods) добавляет пользовательский код в методы теста.  
  
7.  Команда[Вставить паузу до](#CodedUITestEditor_InsertDelay) позволяет вставить перед действием пользовательского интерфейса паузу, длительность которой задается в миллисекундах.  
  
8.  [Найти элемент управления пользовательского интерфейса](#CodedUITestEditor_LocateUIControl) определяет расположение элемента управления в пользовательском интерфейсе тестируемого приложения.  
  
9. Команда [Найти все](#CodedUITestEditor_LocateDecendants) позволяет просмотреть изменения свойств элемента управления и другие существенные изменения, которые выполнены для элементов управления приложения.  
  
## <a name="how-do-i-do-this"></a>Инструкции  
 В [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]открытие файла UIMap.uitest, соответствующего закодированному тесту пользовательского интерфейса в проекте закодированных тестов пользовательского интерфейса, автоматически отобразит закодированный тест пользовательского интерфейса в редакторе закодированных тестов пользовательского интерфейса. Следующие процедуры описывают, как можно найти и отредактировать методы тестов, свойства действий пользовательского интерфейса и элементы управления, используя контекстное меню и панель инструментов редактора.  
  
## <a name="open-a-coded-ui-test"></a>Открытие кодированного теста пользовательского интерфейса  
 Вы можете просмотреть и отредактировать закодированный тест пользовательского интерфейса на основе Visual C# и Visual Basic, используя редактор закодированных тестов пользовательского интерфейса.  
  
 ![Контекстное меню "Изменить с помощью построителя закодированных тестов пользовательского интерфейса"](../test/media/editcodeduitest.png "EditCodedUITest")  
  
 В обозревателе решений откройте контекстное меню для **UIMap.uitest** и выберите **Открыть**. Закодированный тест пользовательского интерфейса откроется в редакторе закодированных тестов пользовательского интерфейса. Теперь можно просматривать и редактировать записанные методы, действия и соответствующие элементы управления в закодированном тесте пользовательского интерфейса.  
  
> [!TIP]
>  При выборе действия пользовательского интерфейса, расположенного в методе в области **действий пользовательского интерфейса** , соответствующий элемент управления выделяется. Вы также можете изменять свойства действия или элемента управления пользовательского интерфейса.  
  
 *Я не вижу* редактор закодированных тестов пользовательского интерфейса.  
 Возможно, вы используете версию Visual Studio Enterprise до 2012. Редактор закодированных тестов пользовательского интерфейса также доступен в пакете дополнительных компонентов Visual Studio Feature Pack 2 2010 с подпиской MSDN. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Microsoft Visual Studio 2010 Feature Pack 2](http://go.microsoft.com/fwlink/?LinkID=204119).  
  
##  <a name="CodedUITestEditor_EditActionAndControlProperties"></a> Изменение свойств действия пользовательского интерфейса и соответствующих свойств элемента управления  
 В редакторе закодированных тестов пользовательского интерфейса можно быстро найти и просмотреть все действия пользовательского интерфейса в методах теста. При выборе действия пользовательского интерфейса в редакторе соответствующий элемент управления автоматически выделяется. Аналогичным образом при выборе элемента управления выделяются связанные действия пользовательского интерфейса. Таким образом, если выбрать действие пользовательского интерфейса или элемент управления, в окне свойств можно легко изменить соответствующие ему свойства.  
  
 ![Свойства действия пользовательского интерфейса](../test/media/codeduiedituiaction.png "CodedUIEditUIAction")  
Изменение свойств действия пользовательского интерфейса  
  
 Для изменения свойств действия пользовательского интерфейса, в области **Действие пользовательского интерфейса** разверните метод теста, который содержит действие пользовательского интерфейса, свойства для которого необходимо изменить, и выделите действие пользовательского интерфейса, а затем измените свойства с помощью окна свойств.  
  
 Например, если сервер недоступен и имеется действие пользовательского интерфейса, связанное с веб-браузером, сообщающее **Перейти на веб-страницу http://Contoso1/default.aspx**, можно изменить URL-адрес на `'http://Contoso2/default.aspx'`.  
  
 ![Свойства элемента управления](../test/media/codeduitestcontrolprop.png "CodedUITestControlProp")  
Изменение свойств элемента управления  
  
 Изменение свойств для элемента управления происходит таким же образом, как и изменение действий пользовательского интерфейса. В области **Карта элементов управления ИП** выберите элемент управления, который требуется отредактировать, и измените его свойства с помощью окна свойств.  
  
 Например, разработчик мог изменить свойство **(ID)** элемента управления "Кнопка" в исходном коде для тестируемого приложения с idSubmit на idLogin. Если свойство **(ID)** в приложении изменено, закодированный тест пользовательского интерфейса не сможет обнаружить кнопку и завершится с ошибкой. В этом случае можно открыть коллекцию **Свойства поиска** и изменить свойство **Id** , чтобы оно соответствовало новому значению, которое разработчик использовал в приложении. Можно также изменить значение свойства **Понятное имя** Submit на Login. Вследствие этого изменения соответствующее действие пользовательского интерфейса в редакторе закодированных тестов пользовательского интерфейса изменяется с "Нажмите кнопку Submit" на "Нажмите кнопку Login".  
  
 После выполнения изменений, сохраните изменения в файл UIMap.Designer, щелкнув **Сохранить** на панели инструментов [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] .  
  
 *Что еще мне нужно знать?*  
 **Советы**  
  
-   ![Совет](~/test/media/tip.png "Совет") Если окно свойств не отображается, нажмите и удерживайте **ALT** при нажатии клавиши **ВВОД** или нажмите клавишу **F4**.  
  
-   ![Совет](~/test/media/tip.png "Совет") Чтобы отменить изменения свойств, выберите команду **Отменить** в меню **Правка** или нажмите клавиши CTRL+Z.  
  
-   ![Совет](~/test/media/tip.png "Совет") Можно использовать кнопку **Найти** на панели инструментов в редакторе закодированных тестов пользовательского интерфейса, чтобы открыть инструмент поиска и замены в Visual Studio. Для поиска элемента управления можно воспользоваться кнопкой "Найти" на панели инструментов в редакторе закодированных тестов пользовательского интерфейса. Например, можно попытаться найти "Нажмите кнопку Login". Такой способ удобно применять в больших тестах. Обратите внимание, что вы не можете использовать функцию замены в инструменте поиска и замены в редакторе закодированных тестов пользовательского интерфейса. Дополнительные сведения см. в разделе [Поиск и замена текста](../ide/finding-and-replacing-text.md).  
  
-   ![Совет](~/test/media/tip.png "Совет") В некоторых случаях может быть сложно представить, где находятся элементы управления пользовательского интерфейса тестируемого приложения. Одна из возможностей в редакторе закодированных тестов пользовательского интерфейса заключается в том, что вы можете выбрать элемент управления, перечисленный в карте элементов управления пользовательского интерфейса, и посмотреть его расположение в тестируемом приложении. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Поиск элемента управления пользовательского интерфейса в тестируемом приложении](#CodedUITestEditor_LocateUIControl) далее в этой статье.  
  
-   ![Совет](~/test/media/tip.png "Совет") Может потребоваться развернуть контейнерный элемент управления, содержащий элемент управления, который требуется изменить. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Определение расположения элемента управления и его потомков](#CodedUITestEditor_LocateDecendants) далее в этой статье.  
  
##  <a name="CodedUITestEditor_DeleteUIActions"></a> Удаление ненужных действий пользовательского интерфейса  
 Вы можете легко удалить ненужные действия пользовательского интерфейса в закодированном тесте пользовательского интерфейса.  
  
 ![Удаление действия пользовательского интерфейса](../test/media/codeduideleteuiaction.png "CodedUIDeleteUIAction")  
  
 В области **действия пользовательского интерфейса** разверните метод теста, содержащий действие пользовательского интерфейса, которое требуется удалить. Откройте контекстное меню для действия пользовательского интерфейса и выберите **Удалить**.  
  
##  <a name="CodedUITestEditor_SplitMethods"></a> Разбиение метода теста на два отдельных метода  
 Можно разбить метод теста, чтобы уточнить или распределить действия пользовательского интерфейса. Например, в тесте может быть один метод теста с действиями пользовательского интерфейса в двух контейнерных элементах управления. Действия пользовательского интерфейса можно разбить на модули в двух методах, соответствующих одному контейнеру.  
  
 ![Разделение метода теста](../test/media/codeduitestsplitmethod1.png "CodedUITestSplitMethod1")  
  
 ![Два метода теста](../test/media/codeduitestsplitmethod2.png "CodedUITestSplitMethod2")  
  
 В области **Действие пользовательского интерфейса** разверните метод теста, который требуется разбить на два отдельных метода, и выберите действие пользовательского интерфейса, в котором должен начаться новый метод теста. Или откройте контекстное меню для действия пользовательского интерфейса, а затем выберите **Разделить и поместить в новый метод**, или нажмите кнопку **Разделить и поместить в новый метод** на панели инструментов редактора закодированных тестов пользовательского интерфейса. Новый метод теста отображается в области действий пользовательского интерфейса. Она содержит действия пользовательского интерфейса, начиная с действия, в котором было указано разделение.  
  
 После выполнения разделения метода сохраните изменения в файл UIMap.Designer, щелкнув **Сохранить** на панели инструментов [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] .  
  
 *Что еще мне нужно знать?*  
 **Важные вопросы**  
  
-   ![Значок предупреждения](~/test/media/caution.gif "предупреждение") **Предупреждение.** В случае разделения метода необходимо изменить любой код, который вызывает существующий метод, так, чтобы он также вызывал новый метод, который планируется создать, если при этом требуется включить эти действия пользовательского интерфейса. Если разделить метод, откроется диалоговое окно Microsoft Visual Studio. Оно предупреждает, что необходимо изменить любой код, который вызывает существующий метод, чтобы он также вызывал новый метод, который вы собираетесь создать. Выберите **Да**.  
  
 **Советы**  
  
-   ![Совет](~/test/media/tip.png "Совет") Чтобы отменить разделение, выберите команду **Отменить** в меню **Правка** или нажмите клавиши CTRL+Z.  
  
-   ![Совет](~/test/media/tip.png "Совет") Вы можете переименовать новый метод. Выберите метод в области действий пользовательского интерфейса и на панели редактора закодированных тестов пользовательского интерфейса нажмите кнопку **Переименовать** .  
  
     -или-  
  
     Откройте контекстное меню для нового метода теста и выберите **Переименовать**.  
  
     Откроется диалоговое окно Microsoft Visual Studio. Оно предупреждает, что необходимо изменить любой код, ссылающийся на этот метод. Выберите **Да**.  
  
##  <a name="CodedUITestEditor_MoveMethods"></a> Перемещение метода теста в файл UIMap для упрощения настройки  
 Если определяется, что один из методов теста в закодированном тесте пользовательского интерфейса требует пользовательский код, необходимо переместить его в файл UIMap.cs или файл UIMap.vb. В противном случае код будет перезаписан при повторной компиляции закодированного теста пользовательского интерфейса. Если вы не перемещаете метод, пользовательский код перезаписывается каждый раз, когда выполняется повторная компиляция теста.  
  
 В области **Действие с ИП** выберите метод теста, который требуется переместить в файл UIMap.cs или UIMap.vb file, чтобы упростить функциональность пользовательского кода. В этом случае он не будет переписываться при каждой компиляции кода теста. После этого нажмите кнопку **Переместить код** на панели инструментов редактора закодированных тестов пользовательского интерфейса или откройте контекстное меню для метода теста и выберите **Переместить код**. Метод теста удаляется из файла UIMap.uitest и перестает отображаться в области "Действия с ИП". Чтобы внести изменения в перемещенный тестовый файл, откройте файл UIMap.cs или the UIMap.vb в обозревателе решений.  
  
 Сохраните изменения в файл UIMap.Designer после выполнения перемещения метода, щелкнув **Сохранить** на панели инструментов [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] .  
  
 *Что еще мне нужно знать?*  
 **Важные вопросы**  
  
-   ![Значок предупреждения](~/test/media/caution.gif "предупреждение") **Предупреждение.** После перемещения метода его нельзя изменять в редакторе закодированных тестов пользовательского интерфейса. Для добавления и обслуживания пользовательского кода следует использовать редактор кода. Если переместить метод, откроется диалоговое окно Microsoft Visual Studio. В нем отобразится предупреждение о том, что метод будет перемещен из файла UIMap.uitest в файл UIMap.cs, после чего метод нельзя будет изменять в редакторе закодированных тестов пользовательского интерфейса. Выберите **Да**.  
  
 **Советы**  
  
-   ![Совет](~/test/media/tip.png "Совет")Чтобы отменить перемещение, выберите команду **Отменить** в меню **Правка** или нажмите клавиши CTRL+Z. Однако затем вы должны вручную удалить этот код в файле UIMap.cs или UIMap.vb.  
  
##  <a name="CodedUITestEditor_LocateUIControl"></a> Locating a UI Control in the application under test  
 В некоторых случаях представить, где находятся элементы управления пользовательского интерфейса тестируемого приложения, может быть сложно. Одна из возможностей в редакторе закодированных тестов пользовательского интерфейса заключается в том, что вы можете выбрать элемент управления, перечисленный в карте элементов управления пользовательского интерфейса, и посмотреть его расположение в тестируемом приложении. С помощью функции **Найти элемент управления пользовательского интерфейса** в тестируемом приложении можно также проверять изменения свойств поиска, внесенные в элемент управления.  
  
 ![Поиск элемента управления пользовательского интерфейса](~/test/media/codeduilocatecontrol.png "CodedUILocateControl")  
  
 ![Элемент управления, расположенный в тестируемом приложении](~/test/media/codeduilocatecontrol2.png "CodedUILocateControl2")  
  
 В области **карты элементов управления пользовательского интерфейса** выберите элемент управления, который требуется найти в приложении, связанном с тестом. Затем откройте контекстное меню для элемента управления, а затем выберите **Найти элемент управления ИП**. В тестируемом приложении этот элемент управления выделяется синей рамкой.  
  
 *Что еще мне нужно знать?*  
 **Важные вопросы**  
  
-   ![Значок предупреждения](~/test/media/caution.gif "предупреждение") **Предупреждение.** Прежде чем приступать к поиску элемента управления пользовательского интерфейса, убедитесь, что связанное с тестом приложение запущено.  
  
 **Советы**  
  
-   ![Совет](~/test/media/tip.png "Совет") Кроме того, можно с помощью команды **Найти все** проверить, что все элементы управления в контейнере можно найти правильно. Эта возможность описана в следующем разделе.  
  
##  <a name="CodedUITestEditor_LocateDecendants"></a> Определение расположения элемента управления и его потомков  
 Можно убедиться, что при тестировании расположение всех элементов управления контейнера в пользовательском интерфейсе приложения определяется правильно. Это может быть полезным при проверке изменений свойств поиска, сделанных в контейнере. Кроме того, если в пользовательском интерфейсе тестируемого приложения были сделаны существенные изменения, можно проверить правильность свойств поиска существующего элемента управления.  
  
 ![Поиск всех дочерних элементов управления](~/test/media/codeduilocateall.png "CodedUILocateAll")  
  
 ![Найдены все элементы управления](../test/media/codeduilocateall2.png "CodedUILocateAll2")  
  
 В области **карты элементов управления пользовательского интерфейса** выберите контейнерный элемент управления, потомки которого требуется найти и просмотреть. Затем откройте контекстное меню элемента управления и выберите команду **Найти все**. Контейнерный элемент управления и все элементы управления, которые являются его потомками, выделяются в редакторе закодированных тестов пользовательского интерфейса зелеными флажками или красным значком "X". Эти метки позволяют понять, были ли элементы управления успешно найдены в тестируемом приложении.  
  
 *Что еще мне нужно знать?*  
 **Важные вопросы**  
  
-   ![Значок предупреждения](~/test/media/caution.gif "предупреждение") **Предупреждение.** Прежде чем приступать к поиску элементов управления пользовательского интерфейса, убедитесь, что связанное с тестом приложение запущено.  
  
##  <a name="CodedUITestEditor_InsertDelay"></a> Вставка задержки перед действием пользовательского интерфейса  
 В некоторых ситуациях может потребоваться, чтобы тест ожидал возникновения определенных событий, например открытия окна, исчезновения строки хода выполнения и т. д. С помощью редактора закодированных тестов пользовательского интерфейса это можно сделать, вставив задержку перед действием пользовательского интерфейса. Можно указать, сколько секунд должна длиться задержка.  
  
 ![Вставка задержки перед действием пользовательского интерфейса](../test/media/codeduidelay.png "CodedUIDelay")  
  
 ![Добавлена задержка продолжительностью 5 секунд](../test/media/codeduidealy2.png "CodedUIDealy2")  
  
 В области **действия пользовательского интерфейса** разверните метод теста, содержащий действие пользовательского интерфейса, перед которым требуется вставить задержку. Выберите действие пользовательского интерфейса. Затем откройте контекстное меню для действия пользовательского интерфейса и выберите команду **Вставить паузу до**. Задержка вставляется и выделяется перед выбранным действием пользовательского интерфейса со следующим текстом: **Ожидать 1 секунду для пользовательской задержки между действиями**. В окне свойств измените значение свойства **Задержка** на необходимое число миллисекунд.  
  
 После выполнения вставки задержки сохраните изменения в файл UIMap.Designer, щелкнув **Сохранить** на панели инструментов [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] .  
  
 *Что еще мне нужно знать?*  
 **Примечания**  
  
-   ![Предварительное требование](~/test/media/prereq.png "Предварительное требование") Если требуется убедиться в доступности конкретного элемента управления перед действием пользовательского интерфейса, рассмотрите возможность добавления пользовательского кода в метод теста с помощью соответствующего метода UITestControl.WaitForControlXXX(). [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Настройка закодированного теста пользовательского интерфейса таким образом, чтобы во время воспроизведения он дожидался определенных событий](../test/making-coded-ui-tests-wait-for-specific-events-during-playback.md).  
  
 **Советы**  
  
-   ![Совет](~/test/media/tip.png "Совет") Если окно свойств не отображается, нажмите и удерживайте ALT при нажатии клавиши ВВОД или нажмите клавишу F4.  
  
## <a name="external-resources"></a>Внешние ресурсы  
  
### <a name="guidance"></a>Руководство  
 [Тестирование непрерывной доставки с Visual Studio 2012 — глава 2. Модульное тестирование. Внутреннее тестирование](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
### <a name="faq"></a>часто задаваемые вопросы  
 [Часто задаваемые вопросы о закодированных тестах пользовательского интерфейса. Часть 1](http://go.microsoft.com/fwlink/?LinkID=230576)  
  
 [Часто задаваемые вопросы о закодированных тестах пользовательского интерфейса. Часть 2](http://go.microsoft.com/fwlink/?LinkID=230578)  
  
### <a name="forum"></a>Форум  
 [Тестирование автоматизации пользовательского интерфейса в Visual Studio (включает CodedUI)](http://go.microsoft.com/fwlink/?LinkID=224497)  
  
## <a name="see-also"></a>См. также  
 [Использование модели автоматизации пользовательского интерфейса для тестирования кода](../test/use-ui-automation-to-test-your-code.md)   
 [Создание закодированных тестов пользовательского интерфейса](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate)   
 [Создание управляемого данными закодированного теста пользовательского интерфейса](../test/creating-a-data-driven-coded-ui-test.md)   
 [Создание закодированного теста пользовательского интерфейса из существующей записи действий](/devops-test-docs/test/generating-a-coded-ui-test-from-an-existing-action-recording)   
 [Пошаговое руководство. Создание, изменение и обслуживание закодированного теста пользовательского интерфейса](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)
