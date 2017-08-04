---
title: "Задача Link | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ForceFileOutput
- VC.Project.VCLinkerTool.LinkStatus
- VC.Project.VCLinkerTool.CLRUnmanagedCodeCheck
- VC.Project.VCLinkerTool.SpecifySectionAttributes
- VC.Project.VCLinkerTool.SupportNobindOfDelayLoadedDLL
- VC.Project.VCLinkerTool.MinimumRequiredVersion
- VC.Project.VCLinkerTool.PerUserRedirection
- VC.Project.VCLinkerTool.CreateHotPatchableImage
- VC.Project.VCLinkerTool.DataExecutionPrevention
- VC.Project.VCLinkerTool.TreatLinkerWarningsAsErrors
- vc.task.link
- VC.Project.VCLinkerTool.ImageHasSafeExceptionHandlers
- VC.Project.VCLinkerTool.CLRSupportLastError
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild (Visual C++), Link task
- Link task (MSBuild (Visual C++))
ms.assetid: 0a61f168-3113-4fa7-83a3-d9142e2a33f8
caps.latest.revision: 12
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: a062b0a929ce812f19bcc6c89594b8f3b2e93b6f
ms.lasthandoff: 04/05/2017

---
# <a name="link-task"></a>Связывание задачи
Создает оболочку для компоновщика Visual C++ link.exe. Компоновщик связывает объектные файлы в формате COFF и библиотеки для создания исполняемого файла (EXE) или библиотеки динамической компоновки (DLL). Дополнительные сведения см. в разделе [Параметры компоновщика](/cpp/build/reference/linker-options).  
  
## <a name="parameters"></a>Параметры  
 В следующей таблице приводятся параметры задачи **Link**. Большинство параметров задачи и некоторые наборы параметров соответствуют параметрам командной строки.  
  
-   **AdditionalDependencies**  
  
     Необязательный параметр типа **String[]**.  
  
     Определяет список входных файлов, добавляемых в команду.  
  
     Дополнительные сведения см. в разделе [Входные файлы LINK](/cpp/build/reference/link-input-files).  
  
-   **AdditionalLibraryDirectories**  
  
     Необязательный параметр типа **String[]**.  
  
     Переопределяет путь к библиотеке среды. Задает имя каталога.  
  
     Дополнительные сведения см. в разделе [Параметр /LIBPATH (дополнительный параметр Libpath)](/cpp/build/reference/libpath-additional-libpath).  
  
-   **AdditionalManifestDependencies**  
  
     Необязательный параметр типа **String[]**.  
  
     Определяет атрибуты, которые будут помещены в раздел `dependency` файла манифеста.  
  
     Дополнительные сведения см. в разделе [Параметр /MANIFESTDEPENDENCY (определение зависимостей манифеста)](/cpp/build/reference/manifestdependency-specify-manifest-dependencies). См. также раздел "Файлы конфигурации издателя" на веб-сайте [MSDN](http://go.microsoft.com/fwlink/?LinkId=737).  
  
-   **AdditionalOptions**  
  
     Необязательный параметр типа **String**.  
  
     Список параметров компоновщика, как они указаны в командной строке. Например, **"***/параметр1 /параметр2 /параметр#*". Этот параметр используется для указания параметров компоновщика, не представленных никаким другим параметром задачи **Link**.  
  
     Дополнительные сведения см. в разделе [Параметры компоновщика](/cpp/build/reference/linker-options).  
  
-   **AddModuleNamesToAssembly**  
  
     Необязательный параметр типа **String[]**.  
  
     Добавление в сборку ссылки на модуль.  
  
     Дополнительные сведения см. в разделе [Параметр /ASSEMBLYMODULE (добавление в сборку модуля MSIL)](/cpp/build/reference/assemblymodule-add-a-msil-module-to-the-assembly).  
  
-   **AllowIsolation**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, операционная система выполняет поиск и загрузку манифеста. Если задано значение `false`, библиотеки DLL загружаются так, как если бы манифеста не было.  
  
     Дополнительные сведения см. в разделе [Параметр /ALLOWISOLATION (поиск манифеста)](/cpp/build/reference/allowisolation-manifest-lookup).  
  
-   **AssemblyDebug**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, создается атрибут **DebuggableAttribute** с отслеживанием отладочной информации и отключается оптимизация JIT. Если задано значение `false`, создается атрибут **DebuggableAttribute** без отслеживания отладочной информации и включается оптимизация JIT.  
  
     Дополнительные сведения см. в разделе [Параметр /ASSEMBLYDEBUG (добавление атрибута DebuggableAttribute)](/cpp/build/reference/assemblydebug-add-debuggableattribute).  
  
-   **AssemblyLinkResource**  
  
     Необязательный параметр типа **String[]**.  
  
     Создается ссылка на ресурс .NET Framework в выходном файле. Файл ресурса не помещается в выходной файл. Укажите имя ресурса.  
  
     Дополнительные сведения см. в разделе [Параметр /ASSEMBLYLINKRESOURCE (компоновка с ресурсом .NET Framework)](/cpp/build/reference/assemblylinkresource-link-to-dotnet-framework-resource).  
  
-   **AttributeFileTracking**  
  
     Неявный параметр **Boolean**.  
  
     Включает более детальное отслеживание файлов для обнаружения инкрементной компоновки. Всегда возвращает значение `true`.  
  
-   **BaseAddress**  
  
     Необязательный параметр типа **String**.  
  
     Задает базовый адрес для сборки программ и библиотек. Задайте имя `{address[,size] | @filename,key}`.  
  
     Дополнительные сведения см. в разделе [Параметр /Base (базовый адрес)](/cpp/build/reference/base-base-address).  
  
-   **BuildingInIDE**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение true, MSBuild вызывается из интегрированной среды разработки. В противном случае MSBuild вызывается из командной строки.  
  
     Этот параметр не имеет эквивалентного параметра компоновщика.  
  
-   **CLRImageType**  
  
     Необязательный параметр типа **String**.  
  
     Определяет тип образа среды CLR.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру компоновщика.  
  
    -   **Default** - *\<отсутствует>*  
  
    -   **ForceIJWImage** - **/CLRIMAGETYPE:IJW**  
  
    -   **ForcePureILImage** - **/CLRIMAGETYPE:PURE**  
  
    -   **ForceSafeILImage** - **/CLRIMAGETYPE:SAFE**  
  
     Дополнительные сведения см. в разделе [Параметр /CLRIMAGETYPE (указание типа образа среды CLR)](/cpp/build/reference/clrimagetype-specify-type-of-clr-image).  
  
-   **CLRSupportLastError**  
  
     Необязательный параметр типа **String**.  
  
     Сохраняет последний код ошибки функций, вызываемых с помощью механизма P/Invoke.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру компоновщика.  
  
    -   **Enabled** - **/CLRSupportLastError**  
  
    -   **Disabled** - **/CLRSupportLastError:NO**  
  
    -   **SystemDlls** - **/CLRSupportLastError:SYSTEMDLL**  
  
     Дополнительные сведения см. в разделе [Параметр /CLRSUPPORTLASTERROR (сохранение кода последней ошибки для вызовов PInvoke)](/cpp/build/reference/clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls).  
  
-   **CLRThreadAttribute**  
  
     Необязательный параметр типа **String**.  
  
     Задает явно атрибут потока для точки входа CLR-программы.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру компоновщика.  
  
    -   **DefaultThreadingAttribute** - **/CLRTHREADATTRIBUTE:NONE**  
  
    -   **MTAThreadingAttribute** - **/CLRTHREADATTRIBUTE:MTA**  
  
    -   **STAThreadingAttribute** - **/CLRTHREADATTRIBUTE:STA**  
  
     Дополнительные сведения см. в разделе [Параметр /CLRTHREADATTRIBUTE (определение атрибута потока среды CLR)](/cpp/build/reference/clrthreadattribute-set-clr-thread-attribute).  
  
-   **CLRUnmanagedCodeCheck**  
  
     Необязательный параметр типа **Boolean**.  
  
     Определяет, будет ли компоновщик применять атрибут **SuppressUnmanagedCodeSecurityAttribute** к созданным компоновщиком вызовам P/Invoke из управляемого кода в библиотеку DLL машинного кода.  
  
     Дополнительные сведения см. в разделе [Параметр /CLRUNMANAGEDCODECHECK (добавление атрибута SupressUnmanagedCodeSecurityAttribute)](/cpp/build/reference/clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute).  
  
-   **CreateHotPatchableImage**  
  
     Необязательный параметр типа **String**.  
  
     Готовит образ к оперативному исправлению.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру компоновщика.  
  
    -   **Enabled** - **/FUNCTIONPADMIN**  
  
    -   **X86Image** - **/FUNCTIONPADMIN:5**  
  
    -   **X64Image** - **/FUNCTIONPADMIN:6**  
  
    -   **ItaniumImage** - **/FUNCTIONPADMIN:16**  
  
     Дополнительные сведения см. в разделе [Параметр /FUNCTIONPADMIN (создание образа, допускающего оперативное обновление)](/cpp/build/reference/functionpadmin-create-hotpatchable-image).  
  
-   **DataExecutionPrevention**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, исполняемый файл будет проверяться на совместимость с компонентом предотвращения выполнения данных Windows.  
  
     Дополнительные сведения см. в разделе [Параметр /NXCOMPAT (совместимость с компонентом предотвращения выполнения данных)](/cpp/build/reference/nxcompat-compatible-with-data-execution-prevention).  
  
-   **DelayLoadDLLs**  
  
     Необязательный параметр типа **String[]**.  
  
     Этот параметр определяет *отложенную загрузку* библиотек DLL. Укажите имя DLL-библиотеки, загрузку которой нужно отложить.  
  
     Дополнительные сведения см. в разделе [Параметр /DELAYLOAD (импорт с отложенной загрузкой)](/cpp/build/reference/delayload-delay-load-import).  
  
-   **DelaySign**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, сборка частично подписывается. Значение по умолчанию `false`.  
  
     Дополнительные сведения см. в разделе [Параметр /DELAYSIGN (частичное подписание сборки)](/cpp/build/reference/delaysign-partially-sign-an-assembly).  
  
-   **Driver**  
  
     Необязательный параметр типа **String**.  
  
     Укажите этот параметр для сборки драйвера режима ядра Windows NT.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру компоновщика.  
  
    -   **NotSet** - *\<none>*  
  
    -   **Driver** - **/Driver**  
  
    -   **UpOnly** - **/DRIVER:UPONLY**  
  
    -   **WDM** - **/DRIVER:WDM**  
  
     Дополнительные сведения см. в разделе [Параметр /DRIVER (драйвер режима ядра Windows NT)](/cpp/build/reference/driver-windows-nt-kernel-mode-driver).  
  
-   **EmbedManagedResourceFile**  
  
     Необязательный параметр типа **String[]**.  
  
     Внедрение файла ресурсов в сборку. Укажите имя нужного файла ресурсов. При необходимости укажите логическое имя, используемое для загрузки ресурса, и параметр **PRIVATE**, который указывает в манифесте сборки, что файл ресурсов является частным.  
  
     Дополнительные сведения см. в разделе [Параметр /ASSEMBLYRESOURCE (внедрение управляемого ресурса)](/cpp/build/reference/assemblyresource-embed-a-managed-resource).  
  
-   **EnableCOMDATFolding**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, разрешается аналогичное свертывание записей COMDAT.  
  
     Дополнительные сведения см. в описании аргумента `ICF[= iterations]` в разделе [Параметр /OPT (оптимизация)](/cpp/build/reference/opt-optimizations).  
  
-   **EnableUAC**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, сведения о контроле учетных записей внедряются в манифест программы.  
  
     Дополнительные сведения см. в разделе [Параметр /MANIFESTUAC (внедрение сведений о контроле учетных записей в манифест)](/cpp/build/reference/manifestuac-embeds-uac-information-in-manifest).  
  
-   **EntryPointSymbol**  
  
     Необязательный параметр типа **String**.  
  
     Определяет функцию точки входа в качестве начального адреса для EXE-файла или DLL. Укажите имя функции в качестве значения параметра.  
  
     Дополнительные сведения см. в разделе [Параметр /Entry (символ точки входа)](/cpp/build/reference/entry-entry-point-symbol).  
  
-   **FixedBaseAddress**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, создается такая программа или DLL-библиотека, которая может загружаться только по предпочтительному базовому адресу.  
  
     Дополнительные сведения см. в разделе [Параметр /FIXED (фиксированный базовый адрес)](/cpp/build/reference/fixed-fixed-base-address).  
  
-   **ForceFileOutput**  
  
     Необязательный параметр типа **String**.  
  
     Предписывает компоновщику создавать EXE-файл или DLL-библиотеку даже в том случае, если на символ есть ссылка, но он не определен или определен многократно.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **Enabled** - **/FORCE**  
  
    -   **MultiplyDefinedSymbolOnly** - **/FORCE:MULTIPLE**  
  
    -   **UndefinedSymbolOnly** - **/FORCE:UNRESOLVED**  
  
     Дополнительные сведения см. в разделе [Параметр /FORCE (принудительный вывод файла)](/cpp/build/reference/force-force-file-output).  
  
-   **ForceSymbolReferences**  
  
     Необязательный параметр типа **String[]**.  
  
     Предписывает компоновщику добавить заданный символ в таблицу символов.  
  
     Дополнительные сведения см. в разделе [Параметр /INCLUDE (принудительные ссылки на символы)](/cpp/build/reference/include-force-symbol-references).  
  
-   **FunctionOrder**  
  
     Необязательный параметр типа **String**.  
  
     Этот параметр позволяет оптимизировать программу, поместив указанные упакованные функции (COMDAT) в образ в предопределенном порядке.  
  
     Дополнительные сведения см. в разделе [Параметр /ORDER (расположение функций по порядку)](/cpp/build/reference/order-put-functions-in-order).  
  
-   **GenerateDebugInformation**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, создается отладочная информация для EXE-файла или библиотеки DLL.  
  
     Дополнительные сведения см. в разделе [Параметр /DEBUG (создание отладочной информации)](/cpp/build/reference/debug-generate-debug-info).  
  
-   **GenerateManifest**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, создается файл манифеста параллельной сборки.  
  
     Дополнительные сведения см. в разделе [Параметр /MANIFEST (создание манифеста параллельной сборки)](/cpp/build/reference/manifest-create-side-by-side-assembly-manifest).  
  
-   **GenerateMapFile**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, создается *файл сопоставления*. Расширение имени файла сопоставления — MAP.  
  
     Дополнительные сведения см. в разделе [Параметр /MAP (создание файла сопоставления)](/cpp/build/reference/map-generate-mapfile).  
  
-   **HeapCommitSize**  
  
     Необязательный параметр типа **String**.  
  
     Указывает объем физической памяти в куче для одновременного выделения.  
  
     Дополнительные сведения см. в описании аргумента `commit` в разделе [Параметр /HEAP (определение размера кучи)](/cpp/build/reference/heap-set-heap-size). См. также описание параметра **HeapReserveSize**.  
  
-   **HeapReserveSize**  
  
     Необязательный параметр типа **String**.  
  
     Определяет общий размер виртуальной памяти, выделяемой для кучи.  
  
     Дополнительные сведения см. в описании аргумента `reserve` в разделе [Параметр /HEAP (определение размера кучи)](/cpp/build/reference/heap-set-heap-size). См. также описание параметра **HeapCommitSize** в этой таблице.  
  
-   **IgnoreAllDefaultLibraries**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, компоновщик удалит одну или несколько стандартных библиотек из списка, в котором выполняется поиск при разрешении внешних ссылок.  
  
     Дополнительные сведения см. в разделе [Параметр /NODEFAULTLIB (игнорировать библиотеки)](/cpp/build/reference/nodefaultlib-ignore-libraries).  
  
-   **IgnoreEmbeddedIDL**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, все атрибуты IDL в исходном коде должны игнорироваться при преобразовании в IDL-файл.  
  
     Дополнительные сведения см. в разделе [Параметр /IGNOREIDL (не преобразовывать атрибуты в MIDL)](/cpp/build/reference/ignoreidl-don-t-process-attributes-into-midl).  
  
-   **IgnoreImportLibrary**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, библиотека импорта, созданная этой конфигурацией, не должна импортироваться в зависимые проекты.  
  
     Этот параметр не соответствует параметру компоновщика.  
  
-   **IgnoreSpecificDefaultLibraries**  
  
     Необязательный параметр типа **String[]**.  
  
     Указывает одно или несколько имен пропускаемых библиотек по умолчанию. Разделяйте библиотеки с помощью точки с запятой.  
  
     Дополнительные сведения см. в разделе [Параметр /NODEFAULTLIB (игнорировать библиотеки)](/cpp/build/reference/nodefaultlib-ignore-libraries).  
  
-   **ImageHasSafeExceptionHandlers**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, компоновщик будет создавать образ только в том случае, если он сможет также создать таблицу безопасных обработчиков исключений образа.  
  
     Дополнительные сведения см. в разделе [Параметр /SAFESEH (образ содержит безопасные обработчики исключений)](/cpp/build/reference/safeseh-image-has-safe-exception-handlers).  
  
-   **ImportLibrary**  
  
     Имя пользовательской библиотеки импорта, которая заменяет библиотеку, заданную по умолчанию.  
  
     Дополнительные сведения см. в разделе [Параметр /IMPLIB (имя библиотеки импорта)](/cpp/build/reference/implib-name-import-library).  
  
-   **KeyContainer**  
  
     Необязательный параметр типа **String**.  
  
     Контейнер, содержащий ключ для подписанной сборки.  
  
     Дополнительные сведения см. в разделе [Параметр /KEYCONTAINER (определение контейнера ключей для подписи сборки)](/cpp/build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly). См. также описание параметра **KeyFile** в этой таблице.  
  
-   **KeyFile**  
  
     Необязательный параметр типа **String**.  
  
     Определяет файл, содержащий ключ для подписанной сборки.  
  
     Дополнительные сведения см. в разделе [Параметр /KEYFILE (определение ключа или пары ключей для подписания сборки)](/cpp/build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly). См. также описание параметра **KeyContainer**.  
  
-   **LargeAddressAware**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, приложение может обрабатывать адреса размером более 2 ГБ.  
  
     Дополнительные сведения см. в разделе [Параметр /LARGEADDRESSAWARE (обработка больших адресов)](/cpp/build/reference/largeaddressaware-handle-large-addresses).  
  
-   **LinkDLL**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, сборка библиотеки DLL будет выполнена в виде основного выходного файла.  
  
     Дополнительные сведения см. в разделе [Параметр /DLL (сборка библиотеки DLL)](/cpp/build/reference/dll-build-a-dll).  
  
-   **LinkErrorReporting**  
  
     Необязательный параметр типа **String**.  
  
     Разрешает передавать данные о внутренних ошибках компилятора (ICE) непосредственно в корпорацию Майкрософт.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **NoErrorReport** - **/ERRORREPORT:NONE**  
  
    -   **PromptImmediately** - **/ERRORREPORT:PROMPT**  
  
    -   **QueueForNextLogin** - **/ERRORREPORT:QUEUE**  
  
    -   **SendErrorReport** - **/ERRORREPORT:SEND**  
  
     Дополнительные сведения см. в разделе [Параметр /ERRORREPORT (создание отчетов о внутренних ошибках компоновщика)](/cpp/build/reference/errorreport-report-internal-linker-errors).  
  
-   **LinkIncremental**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, разрешается инкрементная компоновка.  
  
     Дополнительные сведения см. в разделе [Параметр /INCREMENTAL (инкрементная компоновка)](/cpp/build/reference/incremental-link-incrementally).  
  
-   **LinkLibraryDependencies**  
  
     Необязательный параметр типа **Boolean**.  
  
     Значение `true` указывает, что выходные данные библиотеки из зависимостей проекта включаются автоматически.  
  
     Этот параметр не соответствует параметру компоновщика.  
  
-   **LinkStatus**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, компоновщик отображает индикатор хода выполнения, показывающий в процентах стадию выполнения компоновки.  
  
     Дополнительные сведения см. в описании аргумента `STATUS` в разделе [Параметр /LTCG (создание кода во время компоновки)](/cpp/build/reference/ltcg-link-time-code-generation).  
  
-   **LinkTimeCodeGeneration**  
  
     Необязательный параметр типа **String**.  
  
     Определяет параметры профильной оптимизации.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **Default** - *\<отсутствует>*  
  
    -   **UseLinkTimeCodeGeneration** - **/LTCG**  
  
    -   **PGInstrument** - **/LTCG:PGInstrument**  
  
    -   **PGOptimization** - **/LTCG:PGOptimize**  
  
    -   **PGUpdate**  
  
         \- **/LTCG:PGUpdate**  
  
     Дополнительные сведения см. в разделе [Параметр /LTCG (создание кода во время компоновки)](/cpp/build/reference/ltcg-link-time-code-generation).  
  
-   **ManifestFile**  
  
     Необязательный параметр типа **String**.  
  
     Заменяет имя файла манифеста, заданное по умолчанию, на указанное имя файла.  
  
     Дополнительные сведения см. в разделе [Параметр /MANIFESTFILE (определение имени файла манифеста)](/cpp/build/reference/manifestfile-name-manifest-file).  
  
-   **MapExports**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, компоновщик должен включать экспортированные функции в файл сопоставления.  
  
     Дополнительные сведения см. в описании аргумента `EXPORTS` в разделе [Параметр /MAPINFO (включение сведений в файл сопоставления)](/cpp/build/reference/mapinfo-include-information-in-mapfile).  
  
-   **MapFileName**  
  
     Необязательный параметр типа **String**.  
  
     Заменяет имя файла сопоставления, заданное по умолчанию, на указанное имя файла.  
  
-   **MergedIDLBaseFileName**  
  
     Необязательный параметр типа **String**.  
  
     Определяет имя и расширение IDL-файла.  
  
     Дополнительные сведения см. в разделе [Параметр /IDLOUT (определение имени выходных файлов MIDL)](/cpp/build/reference/idlout-name-midl-output-files).  
  
-   **MergeSections**  
  
     Необязательный параметр типа **String**.  
  
     Определяет объединение разделов в образе. Задайте имя `from-section=to-section`.  
  
     Дополнительные сведения см. в разделе [Параметр /MERGE (объединение разделов)](/cpp/build/reference/merge-combine-sections).  
  
-   **MidlCommandFile**  
  
     Необязательный параметр типа **String**.  
  
     Определяет имя файла, содержащего параметры командной строки MIDL.  
  
     Дополнительные сведения см. в разделе [Параметры /MIDL (определение параметров командной строки MIDL)](/cpp/build/reference/midl-specify-midl-command-line-options).  
  
-   **MinimumRequiredVersion**  
  
     Необязательный параметр типа **String**.  
  
     Задает минимальную необходимую версию подсистемы. Аргументы — десятичные числа в диапазоне от 0 до 65535.  
  
-   **ModuleDefinitionFile**  
  
     Необязательный параметр типа **String**.  
  
     Определяет имя [файла определения модуля](/cpp/build/reference/module-definition-dot-def-files).  
  
     Дополнительные сведения см. в разделе [Параметр /DEF (определение файла определения модуля)](/cpp/build/reference/def-specify-module-definition-file).  
  
-   **MSDOSStubFileName**  
  
     Необязательный параметр типа **String**.  
  
     Присоединяет указанную программу-заглушку MS-DOS к программе Win32.  
  
     Дополнительные сведения см. в разделе [Параметр /STUB (имя файла заглушки MS-DOS)](/cpp/build/reference/stub-ms-dos-stub-file-name).  
  
-   **NoEntryPoint**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, библиотека DLL будет содержать только ресурсы.  
  
     Дополнительные сведения см. в разделе [Параметр /NOENTRY (нет точки входа)](/cpp/build/reference/noentry-no-entry-point).  
  
-   **ObjectFiles**  
  
     Неявный параметр **String[]**.  
  
     Определяет скомпонованные файлы объектов.  
  
-   **OptimizeReferences**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, будут удалены функции и данные, на которые нет ни одной ссылки.  
  
     Дополнительные сведения см. в описании аргумента `REF` в разделе [Параметр /OPT (оптимизация)](/cpp/build/reference/opt-optimizations).  
  
-   **OutputFile**  
  
     Необязательный параметр типа **String**.  
  
     Переопределяет стандартное имя и расположение программы, которую создает компоновщик.  
  
     Дополнительные сведения см. в разделе [Параметр /OUT (имя выходного файла)](/cpp/build/reference/out-output-file-name).  
  
-   **PerUserRedirection**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true` и включена регистрация вывода, все записи в раздел реестра **HKEY_CLASSES_ROOT** будут перенаправляться в раздел **HKEY_CURRENT_USER**.  
  
-   **PreprocessOutput**  
  
     Необязательный параметр `ITaskItem[]`.  
  
     Определяет массив выходных элементов препроцессора, которые могут использоваться и создаваться задачами.  
  
-   **PreventDllBinding**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, Bind.exe не должен привязывать скомпонованный образ.  
  
     Дополнительные сведения см. в разделе [Параметр /ALLOWBIND (запретить привязку DLL)](/cpp/build/reference/allowbind-prevent-dll-binding).  
  
-   **Profile**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, создается выходной файл, который может быть использован для работы с профилировщиком **средств оценки производительности**.  
  
     Дополнительные сведения см. в разделе [Параметр /PROFILE (профилировщик средств оценки производительности)](/cpp/build/reference/profile-performance-tools-profiler).  
  
-   **ProfileGuidedDatabase**  
  
     Необязательный параметр типа **String**.  
  
     Определяет имя PGD-файла, который будет использоваться для хранения сведений о выполняемой программе.  
  
     Дополнительные сведения см. в разделе [Параметр /PGD (указание базы данных для профильной оптимизации)](/cpp/build/reference/pgd-specify-database-for-profile-guided-optimizations).  
  
-   **ProgramDatabaseFile**  
  
     Необязательный параметр типа **String**.  
  
     Определяет имя базы данных программы (PDB), создаваемой компоновщиком.  
  
     Дополнительные сведения см. в разделе [Параметр /PDB (использование базы данных программы)](/cpp/build/reference/pdb-use-program-database).  
  
-   **RandomizedBaseAddress**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, будет создан исполняемый образ, базовый адрес которого может быть случайным образом изменен во время загрузки с помощью технологии *Address space layout randomization* (ASLR), имеющейся в Windows.  
  
     Дополнительные сведения см. в разделе [Параметр /DYNAMICBASE (использование технологии Address space layout randomization)](/cpp/build/reference/dynamicbase-use-address-space-layout-randomization).  
  
-   **RegisterOutput**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, будут регистрироваться основные выходные файлы этой сборки.  
  
-   **SectionAlignment**  
  
     Необязательный параметр типа **Integer**.  
  
     Определяет выравнивание каждого раздела в рамках линейного адресного пространства программы. Значение параметра — число байтов. Равно степени числа два.  
  
     Дополнительные сведения см. в разделе [Параметр /ALIGN (выравнивание разделов)](/cpp/build/reference/align-section-alignment).  
  
-   **SetChecksum**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, будет определяться контрольная сумма в заголовке EXE-файла.  
  
     Дополнительные сведения см. в разделе [Параметр /RELEASE (определение контрольной суммы)](/cpp/build/reference/release-set-the-checksum).  
  
-   **ShowProgress**  
  
     Необязательный параметр типа **String**.  
  
     Определяет уровень детализации отчетов о ходе выполнения для операции компоновки.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **NotSet** - *\<none>*  
  
    -   **LinkVerbose** - **/VERBOSE**  
  
    -   **LinkVerboseLib** - **/VERBOSE:Lib**  
  
    -   **LinkVerboseICF** - **/VERBOSE:ICF**  
  
    -   **LinkVerboseREF** - **/VERBOSE:REF**  
  
    -   **LinkVerboseSAFESEH** - **/VERBOSE:SAFESEH**  
  
    -   **LinkVerboseCLR** - **/VERBOSE:CLR**  
  
     Дополнительные сведения см. в разделе [Параметр /VERBOSE (печать сообщений о ходе выполнения)](/cpp/build/reference/verbose-print-progress-messages).  
  
-   **Sources**  
  
     Обязательный параметр `ITaskItem[]`.  
  
     Определяет массив элементов исходного файла MSBuild, который может использоваться и создаваться задачами.  
  
-   **SpecifySectionAttributes**  
  
     Необязательный параметр типа **String**.  
  
     Определяет атрибуты раздела. Переопределяет атрибуты, которые были заданы при компиляции OBJ-файла для этого раздела.  
  
     Дополнительные сведения см. в разделе [Параметр /SECTION (определение атрибутов раздела)](/cpp/build/reference/section-specify-section-attributes).  
  
-   **StackCommitSize**  
  
     Необязательный параметр типа **String**.  
  
     Определяет объем физической памяти в каждом выделении при выделении дополнительной памяти.  
  
     Дополнительные сведения см. в описании аргумента `commit` в разделе [Параметр /STACK (выделение памяти в стеке)](/cpp/build/reference/stack-stack-allocations).  
  
-   **StackReserveSize**  
  
     Необязательный параметр типа **String**.  
  
     Определяет общий размер виртуальной памяти, выделяемой для стека.  
  
     Дополнительные сведения см. в описании аргумента `reserve` в разделе [Параметр /STACK (выделение памяти в стеке)](/cpp/build/reference/stack-stack-allocations).  
  
-   **StripPrivateSymbols**  
  
     Необязательный параметр типа **String**.  
  
     Определяет создание второго файла базы данных программы (PDB), в котором пропущены символы, не предназначенные для распространения заказчикам. Укажите имя второго файла PDB.  
  
     Дополнительные сведения см. в разделе [Параметр /PDBSTRIPPED (пропуск частных символов)](/cpp/build/reference/pdbstripped-strip-private-symbols).  
  
-   **SubSystem**  
  
     Необязательный параметр типа **String**.  
  
     Указывает среду для исполняемого файла.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **NotSet** - *\<none>*  
  
    -   **Console** - **/SUBSYSTEM:CONSOLE**  
  
    -   **Windows** - **/SUBSYSTEM:WINDOWS**  
  
    -   **Native** - **/SUBSYSTEM:NATIVE**  
  
    -   **EFI Application** - **/SUBSYSTEM:EFI_APPLICATION**  
  
    -   **EFI Boot Service Driver** - **/SUBSYSTEM:EFI_BOOT_SERVICE_DRIVER**  
  
    -   **EFI ROM** - **/SUBSYSTEM:EFI_ROM**  
  
    -   **EFI Runtime** - **/SUBSYSTEM:EFI_RUNTIME_DRIVER**  
  
    -   **WindowsCE** - **/SUBSYSTEM:WINDOWSCE**  
  
    -   **POSIX** - **/SUBSYSTEM:POSIX**  
  
     Дополнительные сведения см. в разделе [Параметр /SUBSYSTEM (определение подсистемы)](/cpp/build/reference/subsystem-specify-subsystem).  
  
-   **SupportNobindOfDelayLoadedDLL**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, компоновщик не будет включать связываемую таблицу IAT в окончательный образ.  
  
     Дополнительные сведения см. в описании аргумента `NOBIND` в разделе [Параметр /DELAY (параметры отложенной загрузки импортов)](/cpp/build/reference/delay-delay-load-import-settings).  
  
-   **SupportUnloadOfDelayLoadedDLL**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, вспомогательная функция отложенной загрузки будет поддерживать явную выгрузку DLL.  
  
     Дополнительные сведения см. в описании аргумента `UNLOAD` в разделе [Параметр /DELAY (параметры отложенной загрузки импортов)](/cpp/build/reference/delay-delay-load-import-settings).  
  
-   **SuppressStartupBanner**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, запрещается отображение сообщения о номере версии и авторских правах при запуске задачи.  
  
     Дополнительные сведения см. в разделе [Параметр /NOLOGO (отмена вывода начального заголовка) (компоновщик)](/cpp/build/reference/nologo-suppress-startup-banner-linker).  
  
-   **SwapRunFromCD**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, операционная система сначала скопирует выходные данные компоновщика в файл подкачки, а затем запустит образ оттуда.  
  
     Дополнительные сведения см. в описании аргумента `CD` в разделе [Параметр /SWAPRUN (загрузка выходных данных компоновщика в файл подкачки)](/cpp/build/reference/swaprun-load-linker-output-to-swap-file). См. также описание параметра **SwapRunFromNET**.  
  
-   **SwapRunFromNET**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, операционная система сначала скопирует выходные данные компоновщика в файл подкачки, а затем запустит образ оттуда.  
  
     Дополнительные сведения см. в описании аргумента `NET` в разделе [Параметр /SWAPRUN (загрузка выходных данных компоновщика в файл подкачки)](/cpp/build/reference/swaprun-load-linker-output-to-swap-file). См. также описание параметра **SwapRunFromCD** в этой таблице.  
  
-   **TargetMachine**  
  
     Необязательный параметр типа **String**.  
  
     Задает целевую платформу программы или DLL.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **NotSet** - *\<none>*  
  
    -   **MachineARM** - **/MACHINE:ARM**  
  
    -   **MachineEBC** - **/MACHINE:EBC**  
  
    -   **MachineIA64** - **/MACHINE:IA64**  
  
    -   **MachineMIPS** - **/MACHINE:MIPS**  
  
    -   **MachineMIPS16** - **/MACHINE:MIPS16**  
  
    -   **MachineMIPSFPU** - **/MACHINE:MIPSFPU**  
  
    -   **MachineMIPSFPU16** - **/MACHINE:MIPSFPU16**  
  
    -   **MachineSH4** - **/MACHINE:SH4**  
  
    -   **MachineTHUMB** - **/MACHINE:THUMB**  
  
    -   **MachineX64** - **/MACHINE:X64**  
  
    -   **MachineX86** - **/MACHINE:X86**  
  
     Дополнительные сведения см. в разделе [Параметр /MACHINE (определение целевой платформы)](/cpp/build/reference/machine-specify-target-platform).  
  
-   **TerminalServerAware**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, будет установлен флаг в поле IMAGE_OPTIONAL_HEADER DllCharacteristics в необязательном заголовке образа программы. Если этот флаг установлен, сервер терминалов не будет вносить определенные изменения в приложение.  
  
     Дополнительные сведения см. в разделе [Параметр /TSAWARE (создание приложения, поддерживающего сервер терминалов)](/cpp/build/reference/tsaware-create-terminal-server-aware-application).  
  
-   **TrackerLogDirectory**  
  
     Необязательный параметр типа **String**.  
  
     Задает каталог журнала отслеживания.  
  
-   **TreatLinkerWarningAsErrors**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, выходной файл не будет создан в случае, если компоновщик выдаст предупреждение.  
  
     Дополнительные сведения см. в разделе [Параметр /WX (обработка предупреждений компоновщика как ошибок)](/cpp/build/reference/wx-treat-linker-warnings-as-errors).  
  
-   **TurnOffAssemblyGeneration**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, образ текущего выходного файла будет создан без сборки .NET Framework.  
  
     Дополнительные сведения см. в разделе [Параметр /NOASSEMBLY (создание модуля MSIL)](/cpp/build/reference/noassembly-create-a-msil-module).  
  
-   **TypeLibraryFile**  
  
     Необязательный параметр типа **String**.  
  
     Определяет имя и расширение TLB-файла. Укажите имя файла или путь и имя файла.  
  
     Дополнительные сведения см. в разделе [Параметр /TLBOUT (имя TLB-файла)](/cpp/build/reference/tlbout-name-dot-tlb-file).  
  
-   **TypeLibraryResourceID**  
  
     Необязательный параметр типа **Integer**.  
  
     Определяет заданное пользователем значение для библиотеки типов, созданной компоновщиком. Укажите значение типа от 1 до 65535.  
  
     Дополнительные сведения см. в разделе [Параметр /TLBID (указание идентификатора ресурса для TypeLib)](/cpp/build/reference/tlbid-specify-resource-id-for-typelib).  
  
-   **UACExecutionLevel**  
  
     Необязательный параметр типа **String**.  
  
     Определяет запрашиваемый уровень выполнения для приложения, запускаемого вместе с контролем учетных записей пользователей.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **AsInvoker** - `level='asInvoker'`  
  
    -   **HighestAvailable** - `level='highestAvailable'`  
  
    -   **RequireAdministrator** - `level='requireAdministrator'`  
  
     Дополнительные сведения см. в описании аргумента `level` в разделе [Параметр /MANIFESTUAC (внедрение сведений о контроле учетных записей в манифест)](/cpp/build/reference/manifestuac-embeds-uac-information-in-manifest).  
  
-   **UACUIAccess**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, приложение обходит уровни защиты пользовательского интерфейса и передает данные, введенные пользователем, окнам на рабочем столе, имеющим более высокий уровень разрешений, в противном случае — `false`.  
  
     Дополнительные сведения см. в описании аргумента `uiAccess` в разделе [Параметр /MANIFESTUAC (внедрение сведений о контроле учетных записей в манифест)](/cpp/build/reference/manifestuac-embeds-uac-information-in-manifest).  
  
-   **UseLibraryDependencyInputs**  
  
     Необязательный параметр типа **Boolean**.  
  
     Если задано значение `true`, будут использоваться входные данные библиотекаря вместо самого файла библиотеки при компоновке выходных данных библиотек для зависимостей проекта.  
  
-   **Version**  
  
     Необязательный параметр типа **String**.  
  
     Укажите номер версии в заголовке EXE-файла или библиотеки DLL. Укажите директиву "`major[.minor]`". Аргументы `major` и `minor` — десятичные числа от 0 до 65535.  
  
     Дополнительные сведения см. в разделе [Параметр /VERSION (сведения о версии)](/cpp/build/reference/version-version-information).  
  
## <a name="see-also"></a>См. также  
 [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)