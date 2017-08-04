---
title: "Элемент &lt;InstallChecks&gt; (загрузчик) | Microsoft Docs"
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
  - "<InstallChecks> - элемент [загрузчик]"
ms.assetid: ad329c87-b0ad-4304-84de-ae9496514c42
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 23
---
# Элемент &lt;InstallChecks&gt; (загрузчик)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Элемент `InstallChecks` поддерживает запуск тестов на локальном компьютере для проверки наличия всех установленных компонентов, необходимых для приложения.  
  
## Синтаксис  
  
```  
<InstallChecks>  
    <AssemblyCheck   
        Property  
        Name  
        PublicKeyToken  
        Version  
        Language  
        ProcessorArchitecture  
    />  
    <RegistryCheck  
        Property  
        Key  
        Value  
    />  
    <ExternalCheck   
        PackageFile  
        Property  
        Arguments  
    />  
    <FileCheck   
        Property  
        FileName  
        SearchPath  
        SpecialFolder  
        SearchDepth  
    />  
    <MsiProductCheck   
        Property  
        Product  
        Feature  
    />  
    <RegistryFileCheck   
        Property  
        Key  
        Value  
        FileName  
        SearchDepth  
    />  
</InstallChecks>  
```  
  
## AssemblyCheck  
 Этот элемент является необязательным дочерним элементом элемента `InstallChecks`.  Для каждого экземпляра `AssemblyCheck` загрузчик проверит, существует ли сборка, заданная этим элементом, в глобальном кэше сборок \(GAC\).  Он не содержит элементов и включает следующие атрибуты.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`Property`|Обязательный.  Имя свойства для хранения результата.  На это свойство может ссылаться тест в элементе `InstallConditions`, который является дочерним по отношению к элементу `Command`.  Дополнительные сведения см. в разделе [Элемент \<Commands\>](../deployment/commands-element-bootstrapper.md).|  
|`Name`|Обязательный.  Полное имя проверяемой сборки.|  
|`PublicKeyToken`|Обязательный.  Сокращенное название открытого ключа, связанного с этой сборкой со строгим именем.  Для всех сборок, хранящихся в глобальном кэше сборок, необходимо указывать имя, номер версии и открытый ключ.|  
|`Version`|Обязательный.  Версия сборки.<br /><br /> Номер версии записывается в формате \<*основной номер версии* \>.\<*дополнительный номер версии* \>.\<*версия построения*\>.\<*версия редакции*\>.|  
|`Language`|Необязательный.  Язык для локализованной сборки.  По умолчанию используется значение `neutral`.|  
|`ProcessorArchitecture`|Необязательный.  Процессор компьютера, для которого предназначена эта установка.  По умолчанию используется значение `msil`.|  
  
## ExternalCheck  
 Этот элемент является необязательным дочерним элементом элемента `InstallChecks`.  Для каждого экземпляра `ExternalCheck` загрузчик будет выполнять именованную внешнюю программу в отдельном процессе и сохранить ее код выхода в свойстве, заданном в `Property`.  `ExternalCheck` полезен для реализации проверок сложных зависимостей, или когда единственным способом проверки существования компонента является создание его экземпляра.  
  
 Элемент `ExternalCheck` не содержит элементов и включает следующие атрибуты.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`Property`|Обязательный.  Имя свойства для хранения результата.  На это свойство может ссылаться тест в элементе `InstallConditions`, который является дочерним по отношению к элементу `Command`.  Дополнительные сведения см. в разделе [Элемент \<Commands\>](../deployment/commands-element-bootstrapper.md).|  
|`PackageFile`|Обязательный.  Внешняя исполняемая программа.  Эта программа должна быть включена в состав установочного пакета.|  
|`Arguments`|Необязательный.  Аргументы командной строки для исполняемого файла `PackageFile`.|  
  
## FileCheck  
 Этот элемент является необязательным дочерним элементом элемента `InstallChecks`.  Для каждого экземпляра `FileCheck` начальный загрузчик определяет, существует ли именованный файл, и возвращает номер версии файла.  Если файл не имеет номера версии, то загрузчик устанавливает для свойства с именем `Property` значение 0.  Если файл не существует, то `Property` не присваивается какое\-либо значение.  
  
 Элемент `FileCheck` не содержит элементов и включает следующие атрибуты.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`Property`|Обязательный.  Имя свойства для хранения результата.  На это свойство может ссылаться тест в элементе `InstallConditions`, который является дочерним по отношению к элементу `Command`.  Дополнительные сведения см. в разделе [Элемент \<Commands\>](../deployment/commands-element-bootstrapper.md).|  
|`FileName`|Обязательный.  Имя файла для поиска.|  
|`SearchPath`|Обязательный.  Диск или папка, где выполняется поиск файла.  Необходимо указать относительный путь, если установлено значение `SpecialFolder`; в остальных случаях необходимо указывать абсолютный путь.|  
|`SpecialFolder`|Необязательный.  Папка, представляющая особую значимость либо для Windows, либо для приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  По умолчанию `SearchPath` интерпретируется как абсолютный путь.  Допустимые значения:<br /><br /> `AppDataFolder`.  Папка данных для приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]; относится к текущему пользователю.<br /><br /> `CommonAppDataFolder`.  Папка с данными приложения, используемая всеми пользователями.<br /><br /> `CommonFilesFolder`.  Папка общих файлов для текущего пользователя.<br /><br /> `LocalDataAppFolder`.  Папка с данными для неперемещающихся приложений.<br /><br /> `ProgramFilesFolder`.  Стандартная папка Program Files для 32\-разрядных приложений.<br /><br /> `StartUpFolder`.  Папка, содержащая все приложения, запускаемые при запуске системы.<br /><br /> `SystemFolder`.  Папка, содержащая 32\-разрядные системные библиотеки DLL.<br /><br /> `WindowsFolder`.  Папка с системными файлами установки Windows.<br /><br /> `WindowsVolume`.  Диск или раздел с системными файлами установки Windows.|  
|`SearchDepth`|Необязательный.  Глубина поиска именованного файла в подпапках.  Поиск выполняется преимущественно в глубину.  По умолчанию задано значение 0, ограничивающее поиск папкой верхнего уровня, заданной параметрами `SpecialFolder` и **SearchPath**.|  
  
## MsiProductCheck  
 Этот элемент является необязательным дочерним элементом элемента `InstallChecks`.  Для каждого экземпляра `MsiProductCheck` начальный загрузчик проверяет, завершена ли установка указанного продукта с помощью установщика Windows.  Значение свойства задается в зависимости от состояния установленного продукта.  Положительное значение указывает на то, что продукт установлен, а 0 или \-1 — на то, что продукт не установлен.  \(См. также описание функции MsiQueryFeatureState в документации по пакету установщика Windows SDK.\) .  Если установщик Windows не установлен на компьютере, то свойство `Property` не задается.  
  
 Элемент `MsiProductCheck` не содержит элементов и включает следующие атрибуты.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`Property`|Обязательный.  Имя свойства для хранения результата.  На это свойство может ссылаться тест в элементе `InstallConditions`, который является дочерним по отношению к элементу `Command`.  Дополнительные сведения см. в разделе [Элемент \<Commands\>](../deployment/commands-element-bootstrapper.md).|  
|`Product`|Обязательный.  GUID для установленного продукта.|  
|`Feature`|Необязательный.  GUID отдельной функции установленного приложения.|  
  
## RegistryCheck  
 Этот элемент является необязательным дочерним элементом элемента `InstallChecks`.  Для каждого экземпляра `RegistryCheck` начальный загрузчик проверяет существование указанного раздела реестра или существование указанного значения.  
  
 Элемент `RegistryCheck` не содержит элементов и включает следующие атрибуты.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`Property`|Обязательный.  Имя свойства для хранения результата.  На это свойство может ссылаться тест в элементе `InstallConditions`, который является дочерним по отношению к элементу `Command`.  Дополнительные сведения см. в разделе [Элемент \<Commands\>](../deployment/commands-element-bootstrapper.md).|  
|`Key`|Обязательный.  Имя раздела реестра.|  
|`Value`|Необязательный.  Имя извлекаемого значения реестра.  По умолчанию возвращается текст значения по умолчанию.  Объект `Value` должен иметь тип String или DWORD.|  
  
## RegistryFileCheck  
 Этот элемент является необязательным дочерним элементом элемента `InstallChecks`.  Для каждого экземпляра `RegistryFileCheck` начальный загрузчик извлекает номер версии указанного файла, сначала извлекая путь к файлу из указанного раздела реестра.  Это особенно полезно в случаях, когда требуется найти файл в каталоге, заданном в виде значения в реестре.  
  
 Элемент `RegistryFileCheck` не содержит элементов и включает следующие атрибуты.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`Property`|Обязательный.  Имя свойства для хранения результата.  На это свойство может ссылаться тест в элементе `InstallConditions`, который является дочерним по отношению к элементу `Command`.  Дополнительные сведения см. в разделе [Элемент \<Commands\>](../deployment/commands-element-bootstrapper.md).|  
|`Key`|Обязательный.  Имя раздела реестра.  Его значение интерпретируется как путь к файлу, если не задан атрибут `File`.  Если этот раздел не существует, то свойство `Property` не задается.|  
|`Value`|Необязательный.  Имя извлекаемого значения реестра.  По умолчанию возвращается текст значения по умолчанию.  Объект `Value` должен быть строкой.|  
|`FileName`|Необязательный.  Имя файла.  Если оно указано, то значение, полученное из раздела реестра, понимается как путь к каталогу, и это имя добавляется к нему.  Если оно не указано, то значение, возвращаемое из реестра, понимается как полный путь к файлу.|  
|`SearchDepth`|Необязательный.  Глубина поиска именованного файла в подпапках.  Поиск выполняется преимущественно в глубину.  По умолчанию задано значение 0, ограничивающее поиск папкой верхнего уровня, заданной значением раздела реестра.|  
  
## Заметки  
 Элементы, включенные в элемент `InstallChecks`, задают условия запуска тестов, но не выполняют сами тесты.  Чтобы выполнить тест, необходимо создать элемент `Command` в элементе `Commands`.  
  
## Пример  
 В следующем примере кода показано использование элемента `InstallChecks` в файле продукта [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
```  
<InstallChecks>  
    <ExternalCheck Property="DotNetInstalled" PackageFile="dotnetchk.exe" />  
    <RegistryCheck Property="IEVersion" Key="HKLM\Software\Microsoft\Internet Explorer" Value="Version" />  
</InstallChecks>  
```  
  
## InstallConditions  
 Результатом проверки `InstallChecks` являются свойства.  На основании этих свойств элемент `InstallConditions` определяет, следует ли выполнить, пропустить или прервать установку пакета.  В следующей таблице перечислены условия `InstallConditions`:  
  
|||  
|-|-|  
|`FailIf`|Если любому из условий `FailIf` присвоено значение true, установка пакета будет прервана.  Остальные условия не проверяются.|  
|`BypassIf`|Если любому из условий `BypassIf` присвоено значение true, установка пакета пропускается.  Остальные условия не проверяются.|  
  
## Предопределенные свойства  
 В следующей таблице представлены элементы `BypassIf` и `FailIf`.  
  
|Свойство.|Примечания|Возможные значения|  
|---------------|----------------|------------------------|  
|`Version9X`|Номер версии операционной системы Windows 9X.|4.10 \= Windows 98|  
|`VersionNT`|Номер версии операционной системы семейства Windows NT.|Major.Minor.ServicePack<br /><br /> 5.0 \= Windows 2000<br /><br /> 5.1.0 \= Windows XP<br /><br /> 5.1.2 \= Windows XP Professional c пакетом обновления 2<br /><br /> 5.2.0 \= Windows Server 2003|  
|`VersionNT64`|Номер версии 64\-разрядной операционной системы семейства Windows NT.|См. выше.|  
|`VersionMsi`|Номер версии службы установщика Windows.|2.0 \= Установщик Windows 2.0|  
|`AdminUser`|Наличие у пользователя привилегий администратора в операционной системе семейства Windows NT.|0 \= нет привилегий администратора<br /><br /> 1 \= есть привилегии администратора|  
  
 Например, чтобы заблокировать установку на компьютере под управлением Windows 95, используется следующий код:  
  
```  
<!-- Block install on Windows 95 -->  
    <FailIf Property="Version9X" Compare="VersionLessThan" Value="4.10" String="InvalidPlatform"/>  
```  
  
## См. также  
 [Элемент \<Commands\>](../deployment/commands-element-bootstrapper.md)   
 [Справочные сведения о схеме пакетов и продуктов](../deployment/product-and-package-schema-reference.md)