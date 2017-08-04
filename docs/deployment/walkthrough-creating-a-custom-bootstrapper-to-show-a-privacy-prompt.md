---
title: "Пошаговое руководство. Создание пользовательского загрузчика для вывода окна с предупреждением о конфиденциальности | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "развертывание ClickOnce, необходимые компоненты"
  - "зависимости [платформа .NET Framework], пакет пользовательского загрузчика"
  - "развертывание приложений [Visual Studio], настраиваемые необходимые компоненты"
  - "необходимые компоненты [платформа .NET Framework], пакет пользовательского загрузчика"
  - "развертывание с помощью установщика Windows, необходимые компоненты"
ms.assetid: 2f3edd6a-84d1-4864-a1ae-6a13c5732aae
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 10
---
# Пошаговое руководство. Создание пользовательского загрузчика для вывода окна с предупреждением о конфиденциальности
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Приложения ClickOnce можно настроить таким образом, чтобы автоматически обновлять их при появлении сборок с более новыми версиями файлов или более новых версий сборок.  Чтобы убедиться в том, что пользователи согласны с этим поведением, в программе можно отобразить окно подтверждения.  В этом окне пользователи могут разрешить приложению автоматическое обновление или запретить его.  Если автоматическое обновление приложения не разрешено, оно не устанавливается.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   Visual Studio 2010.  
  
## Создание диалогового окна подтверждения обновления  
 Чтобы отобразить окно подтверждения, следует создать приложение, запрашивающее у пользователя согласие на выполнение автоматических обновлений приложения.  
  
#### Создание диалогового окна подтверждения  
  
1.  В меню **Файл** последовательно выберите пункты **Создать** и **Проект**.  
  
2.  В диалоговом окне **Создать проект** выберите пункт **Windows**, а затем — пункт **Приложение Windows Forms**.  
  
3.  В поле **Имя** введите ConsentDialog, а затем нажмите кнопку **OK**.  
  
4.  Выберите форму в конструкторе.  
  
5.  В окне **Свойства** измените значение свойства **Текст** на Update Consent Dialog.  
  
6.  Перейдите к **панели элементов**, разверните узел **Все формы Windows Forms** и перетащите элемент управления **Label** в форму.  
  
7.  В конструкторе форм щелкните элемент управления Label.  
  
8.  В окне **Свойства** замените значение свойства **Текст** в разделе **Внешний вид** на следующее значение.  
  
     Устанавливаемое приложение проверяет наличие последних обновлений в Интернете.  Нажав кнопку "Принимаю", пользователь разрешает приложению автоматически проверять наличие обновлений в Интернете и устанавливать их.  
  
9. Перейдите на **панель элементов** и перетащите элемент управления **Флажок** в середину формы.  
  
10. В окне **Свойства** замените значение свойства **Текст** в разделе **Структура** на значение "Принимаю".  
  
11. Перейдите на **панель элементов** и перетащите элемент управления **Кнопка** в левый нижний угол формы.  
  
12. В окне **Свойства** замените значение свойства **Текст** в разделе **Структура** на значение "Продолжить".  
  
13. В окне **Свойства** замените значение свойства **\(Имя\)** в разделе **Конструктор** на значение ProceedButton.  
  
14. Перейдите на **панель элементов** и перетащите элемент управления **Кнопка** в правый нижний угол формы.  
  
15. В окне **Свойства** замените значение свойства **Текст** в разделе **Структура** на значение "Отмена".  
  
16. В окне **Свойства** замените значение свойства **\(Имя\)** в разделе **Конструктор** на значение CancelButton.  
  
17. Дважды щелкните флажок **Принимаю** в конструкторе, чтобы создать обработчик событий CheckedChanged.  
  
18. Добавьте следующий код для обработчика событий CheckedChanged в файле кода Form1.  
  
     [!code-cs[ConsentDialog#1](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_1.cs)]
     [!code-vb[ConsentDialog#1](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_1.vb)]  
  
19. Измените конструктор класса, чтобы по умолчанию отключить кнопку **Продолжить**.  
  
     [!code-cs[ConsentDialog#6](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_2.cs)]
     [!code-vb[ConsentDialog#6](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_2.vb)]  
  
20. Добавьте следующий код для логической переменной в файл кода Form1, чтобы отслеживать согласие пользователя на выполнение Интернет\-обновлений.  
  
     [!code-cs[ConsentDialog#3](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_3.cs)]
     [!code-vb[ConsentDialog#3](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_3.vb)]  
  
21. В конструкторе дважды щелкните кнопку **Продолжить**, чтобы создать обработчик событий Click.  
  
22. Добавьте следующий код в обработчик событий Click файла кода Form1 для кнопки **Продолжить**.  
  
     [!code-cs[ConsentDialog#2](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_4.cs)]
     [!code-vb[ConsentDialog#2](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_4.vb)]  
  
23. В конструкторе дважды щелкните кнопку **Отмена**, чтобы создать обработчик событий Click.  
  
24. Добавьте следующий код в обработчик событий Click файла кода Form1 для кнопки **Отмена**.  
  
     [!code-cs[ConsentDialog#4](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_5.cs)]
     [!code-vb[ConsentDialog#4](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_5.vb)]  
  
25. Измените приложение, чтобы вернуть ошибку в том случае, если конечный пользователь не даст своего согласия на Интернет\-обновления.  
  
     Только для разработчиков на Visual Basic:  
  
    1.  В **Обозревателе решений** щелкните элемент **ConsentDialog**.  
  
    2.  В меню **Проект** выберите команду **Добавить модуль** и щелкните элемент **Добавить**.  
  
    3.  Добавьте следующий код в файл кода Module1.vb.  
  
         [!code-vb[ConsentDialog#7](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_6.vb)]  
  
    4.  Откройте меню **Проект**, щелкните команду **Свойства ConsentDialog**, а затем щелкните вкладку **Приложение**.  
  
    5.  Снимите флажок **Включить исполняющую среду**.  
  
    6.  В раскрывающемся меню **Начальный объект** выберите элемент **Module1**.  
  
        > [!NOTE]
        >  Отключение исполняющей среды приводит к отключению следующих функций: визуальных стилей Windows XP, событий приложения, экрана\-заставки, единого экземпляра приложения и пр.  Дополнительные сведения см. в разделе [Страница «Приложение» в конструкторе проектов \(Visual Basic\)](../ide/reference/application-page-project-designer-visual-basic.md).  
  
     Только для разработчиков на Visual C\#:  
  
     Откройте файл кода Program.cs и добавьте следующий код.  
  
     [!code-cs[ConsentDialog#5](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt_7.cs)]  
  
26. В меню **Построение** выберите команду **Построить решение**.  
  
## Создание пользовательского пакета загрузчика  
 Чтобы отобразить окно подтверждения конечным пользователям, можно создать настраиваемый пакет загрузчика для приложения Update Consent Dialog и включить его в число необходимых компонентов для всех приложений ClickOnce.  
  
 Ниже представлены действия по созданию настраиваемого пакета загрузчика путем создания следующих документов:  
  
-   Файл манифеста product.xml, описывающий содержимое загрузчика.  
  
-   Файл манифеста package.xml, описывающий особенности локализации пакета, например строки и условия лицензирования продукта.  
  
-   Документ с условиями лицензии программного обеспечения.  
  
#### Шаг 1. Создание каталога загрузчика  
  
1.  Создайте каталог с именем UpdateConsentDialog в папке %PROGRAMFILES%\\Microsoft SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages.  
  
    > [!NOTE]
    >  Для создания этой папки могут потребоваться полномочия администратора.  
  
2.  Создайте вложенную папку en в каталоге UpdateConsentDialog.  
  
    > [!NOTE]
    >  Создайте каталог для каждого языкового стандарта.  Например, можно добавить вложенные папки для языковых стандартов fr и de.  При необходимости эти каталоги могут содержать строки и языковые пакеты для французского и немецкого языка.  
  
#### Шаг 2. Создание файла манифеста product.xml  
  
1.  Создайте текстовый файл с именем `product.xml`.  
  
2.  Добавьте следующий XML\-код в файл product.xml.  Убедитесь в том, что существующий XML\-код не перезаписывается.  
  
    ```  
    <Product  
      xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
      ProductCode="Microsoft.Sample.EULA">  
      <!-- Defines the list of files to be copied on build. -->  
      <PackageFiles CopyAllPackageFiles="false">  
        <PackageFile Name="ConsentDialog.exe"/>  
      </PackageFiles>  
  
      <!-- Defines how to run the Setup package.-->  
      <Commands >  
        <Command PackageFile = "ConsentDialog.exe" Arguments=''>  
          <ExitCodes>  
            <ExitCode Value="0" Result="Success" />  
            <ExitCode Value="-1" Result="Fail" String="AU_Unaccepted" />  
            <DefaultExitCode Result="Fail"   
              FormatMessageFromSystem="true" String="GeneralFailure" />  
          </ExitCodes>  
        </Command>  
      </Commands>  
  
    </Product>  
    ```  
  
3.  Сохраните файл в каталог загрузчика UpdateConsentDialog.  
  
#### Шаг 3. Создание файла манифеста package.xml и условий лицензии  
  
1.  Создайте текстовый файл с именем `package.xml`.  
  
2.  Добавьте в файл package.xml следующий XML\-код, чтобы определить языковой стандарт и добавить условия лицензии программного обеспечения.  Убедитесь в том, что существующий XML\-код не перезаписывается.  
  
    ```  
    <Package   
      xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
      Name="DisplayName"  
      Culture="Culture"  
      LicenseAgreement="eula.rtf">  
      <PackageFiles>  
        <PackageFile Name="eula.rtf"/>  
      </PackageFiles>  
  
      <!-- Defines a localizable string table for error messages. -->  
      <Strings>  
        <String Name="DisplayName">Update Consent Dialog</String>  
        <String Name="Culture">en</String>  
        <String Name="AU_Unaccepted">The automatic update agreement is not accepted.</String>  
        <String Name="GeneralFailure">A failure occurred attempting to launch the setup.</String>  
      </Strings>  
    </Package>  
    ```  
  
3.  Сохраните файл во вложенную папку en каталога загрузчика UpdateConsentDialog.  
  
4.  Создайте документ с именем eula.rtf для условий лицензии.  
  
    > [!NOTE]
    >  В условия лицензии должны входить сведения о лицензировании, гарантиях, ответственности и местном законодательстве.  Эти файлы должны быть привязаны к языковому стандарту, поэтому следует убедиться в том, что файл сохранен в формате, который поддерживает символы MBCS или UNICODE.  Проконсультируйтесь с юридическим отделом вашей компании о содержании условий лицензии для программного обеспечения.  
  
5.  Сохраните документ во вложенную папку en каталога загрузчика UpdateConsentDialog.  
  
6.  При необходимости также создайте файлы манифеста package.xml и документы условий лицензии eula.rtf для каждого языкового стандарта.  Например, если для языковых стандартов fr и de созданы вложенные папки, следует создать отдельные файлы манифеста package.xml и условия лицензии, а затем сохранить их во вложенные папки fr и de.  
  
## Установка приложения согласия на обновления в качестве необходимого компонента  
 Visual Studio позволяет установить приложение согласия на установку в качестве обязательного компонента.  
  
#### Установка приложения согласия на обновления в качестве необходимого компонента  
  
1.  В **Обозревателе решений** щелкните имя приложения, которое требуется развернуть.  
  
2.  В меню **Проект** выберите пункт **Свойства:** *имя\_проекта*.  
  
3.  Перейдите на страницу **Опубликовать**, а затем нажмите кнопку **Необходимые компоненты**.  
  
4.  Выберите элемент **Update Consent Dialog**.  
  
    > [!NOTE]
    >  Для отображения элемента Update Consent Dialog в диалоговом окне "Необходимые компоненты" может потребоваться закрытие и повторное открытие Visual Studio.  
  
5.  Нажмите кнопку **ОК**.  
  
## Создание и тестирование программы установки  
 После установки приложения Update Consent в качестве необходимого компонента можно создать установщик загрузчик для приложения.  
  
#### Создание и тестирование программы установки без установки флажка "Принимаю"  
  
1.  В **Обозревателе решений** щелкните имя приложения, которое требуется развернуть.  
  
2.  В меню **Проект** выберите пункт **Свойства:** *имя\_проекта*.  
  
3.  Перейдите на страницу **Публикации** и щелкните элемент **Опубликовать сейчас**.  
  
4.  Если результат публикации не открывается автоматически, перейдите к результату самостоятельно.  
  
5.  Запустите программу Setup.exe.  
  
     Программа установки отобразит условия лицензии программного обеспечения Update Consent Dialog.  
  
6.  Ознакомьтесь с лицензионным соглашением и нажмите кнопку **Принять**.  
  
     Отображается приложение Update Consent Dialog со следующим текстом: "Устанавливаемое приложение проверяет наличие последних обновлений в Интернете.  Установив флажок «Принимаю», пользователь разрешает приложению автоматически проверять наличие обновлений в Интернете".  
  
7.  Закройте приложение или нажмите кнопку "Отмена".  
  
     Приложение отобразит ошибку: "Произошла ошибка при установке системных компонентов для *имя\_программы*.  Продолжение установки невозможно до тех пор, пока все системные компоненты не будут успешно установлены".  
  
8.  Нажмите кнопку "Подробнее", чтобы отобразить следующее сообщение об ошибке: "Не удалось установить компонент Update Consent Dialog. Получено сообщение об ошибке: «Автоматическое согласие на обновление не принимается». Не удалось установить следующие компоненты: \- Update Consent Dialog"  
  
9. Нажмите кнопку **Закрыть**.  
  
#### Создание и тестирование программы установки с установкой флажка "Принимаю"  
  
1.  В **Обозревателе решений** щелкните имя приложения, которое требуется развернуть.  
  
2.  В меню **Проект** выберите пункт **Свойства:** *имя\_проекта*.  
  
3.  Перейдите на страницу **Публикации** и щелкните элемент **Опубликовать сейчас**.  
  
4.  Если результат публикации не открывается автоматически, перейдите к результату самостоятельно.  
  
5.  Запустите программу Setup.exe.  
  
     Программа установки отобразит условия лицензии программного обеспечения Update Consent Dialog.  
  
6.  Ознакомьтесь с лицензионным соглашением и нажмите кнопку **Принять**.  
  
     Отображается приложение Update Consent Dialog со следующим текстом: "Устанавливаемое приложение проверяет наличие последних обновлений в Интернете.  Установив флажок «Принимаю», пользователь разрешает приложению автоматически проверять наличие обновлений в Интернете".  
  
7.  Установите флажок **Принимаю**, а затем нажмите кнопку **Продолжить**.  
  
     Начнется установка приложения.  
  
8.  Если отобразится диалоговое окно установки приложения, нажмите кнопку **Установить**.  
  
## См. также  
 [Предварительные условия для развертывания приложения](../deployment/application-deployment-prerequisites.md)   
 [Создание пакетов загрузчика](../deployment/creating-bootstrapper-packages.md)   
 [Практическое руководство. Создание манифеста продукта](../deployment/how-to-create-a-product-manifest.md)   
 [Практическое руководство. Создание манифеста пакета](../deployment/how-to-create-a-package-manifest.md)   
 [Справочные сведения о схеме пакетов и продуктов](../deployment/product-and-package-schema-reference.md)