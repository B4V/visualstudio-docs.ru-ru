# [MSBuild](msbuild.md)

## [Новые возможности MSBuild 15.0](what-s-new-in-msbuild-15-0.md)

## [Основные понятия MSBuild](msbuild-concepts.md)

### [Свойства MSBuild](msbuild-properties.md)

#### [Практическое руководство. Использование переменных среды в построении](how-to-use-environment-variables-in-a-build.md)

#### [Практическое руководство. Использование ссылки на имя или расположение файла проекта](how-to-reference-the-name-or-location-of-the-project-file.md)

#### [Практическое руководство. Построение одинаковых исходных файлов с различными параметрами](how-to-build-the-same-source-files-with-different-options.md)

#### [Функции свойств](property-functions.md)

### [Элементы MSBuild](msbuild-items.md)

#### [Практическое руководство. Выбор файлов для построения](how-to-select-the-files-to-build.md)

#### [Практическое руководство. Исключение файлов из построения](how-to-exclude-files-from-the-build.md)

#### [Практическое руководство. Отображение списка элементов, разделенных запятыми](how-to-display-an-item-list-separated-with-commas.md)

#### [Определения элементов](item-definitions.md)

#### [Функции элементов](item-functions.md)

#### [Отслеживание файлов](file-tracking.md)

##### [EndTrackingContext](endtrackingcontext.md)

##### [ResumeTracking](resumetracking.md)

##### [SetThreadCount](setthreadcount.md)

##### [StartTrackingContext](starttrackingcontext.md)

##### [StartTrackingContextWithRoot](starttrackingcontextwithroot.md)

##### [StopTrackingAndCleanup](stoptrackingandcleanup.md)

##### [SuspendTracking](suspendtracking.md)

##### [WriteAllTLogs](writealltlogs.md)

##### [WriteContextTLogs](writecontexttlogs.md)

### [Целевые объекты MSBuild](msbuild-targets.md)

#### [Порядок построения целевого объекта](target-build-order.md)

#### [Добавочные сборки](incremental-builds.md)

#### [Практическое руководство. Выбор цели для первого построения](how-to-specify-which-target-to-build-first.md)

#### [Как использовать одинаковый целевой объект в нескольких файлах проектов](how-to-use-the-same-target-in-multiple-project-files.md)

#### [Практическое руководство. Построение особых целей в решениях с помощью MSBuild.exe](how-to-build-specific-targets-in-solutions-by-using-msbuild-exe.md)

#### [Практическое руководство. Инкрементное построение](how-to-build-incrementally.md)

#### [Практическое руководство. Очистка сборки](how-to-clean-a-build.md)

### [Задачи MSBuild](msbuild-tasks.md)

#### [Написание задач](task-writing.md)

#### [Практическое руководство. Игнорирование ошибок в задачах](how-to-ignore-errors-in-tasks.md)

#### [Практическое руководство. Построение проекта, содержащего ресурсы](how-to-build-a-project-that-has-resources.md)

#### [Встроенные задачи MSBuild](msbuild-inline-tasks.md)

##### [Пошаговое руководство. Создание встроенной задачи](walkthrough-creating-an-inline-task.md)

### [Сравнение свойств и элементов](comparing-properties-and-items.md)

### [Специальные символы в MSBuild](msbuild-special-characters.md)

#### [Как обеспечить пропуск специальных знаков в MSBuild](how-to-escape-special-characters-in-msbuild.md)

#### [Как использовать резервные символы XML в файлах проектов](how-to-use-reserved-xml-characters-in-project-files.md)

## [Дополнительные возможности MSBuild](msbuild-advanced-concepts.md)

### [Пакетная обработка в MSBuild](msbuild-batching.md)

#### [Метаданные элементов в пакетной обработке задач](item-metadata-in-task-batching.md)

#### [Метаданные элементов в пакетной обработке целевых объектов](item-metadata-in-target-batching.md)

### [Преобразования MSBuild](msbuild-transforms.md)

### [Интеграция Visual Studio (MSBuild)](visual-studio-integration-msbuild.md)

#### [Практическое руководство. Расширение процесса построения Visual Studio](how-to-extend-the-visual-studio-build-process.md)

#### [Запуск построения из интегрированной среды разработки](starting-a-build-from-within-the-ide.md)

#### [Регистрация расширений платформы .NET Framework](registering-extensions-of-the-dotnet-framework.md)

### [Параллельное построение нескольких проектов с помощью MSBuild](building-multiple-projects-in-parallel-with-msbuild.md)

#### [Использование нескольких процессоров при построении проектов](using-multiple-processors-to-build-projects.md)

#### [Эффективное использование памяти при построении больших проектов](using-memory-efficiently-when-you-build-large-projects.md)

### [MSBuild: обзор настройки для различных версий](msbuild-multitargeting-overview.md)

#### [Набор инструментов MSBuild (ToolsVersion)](msbuild-toolset-toolsversion.md)

##### [Стандартные и настраиваемые конфигурации наборов инструментов](standard-and-custom-toolset-configurations.md)

##### [Переопределение параметров ToolsVersion](overriding-toolsversion-settings.md)

#### [MSBuild: целевая рабочая среда и целевая платформа](msbuild-target-framework-and-target-platform.md)

#### [Разрешение сборок во время разработки](resolving-assemblies-at-design-time.md)

#### [Настройка целевых платформ и задач](configuring-targets-and-tasks.md)

##### [Практическое руководство. Настройка целевых платформ и задач](how-to-configure-targets-and-tasks.md)

#### [Устранение неполадок, связанных с настройкой для определенных версий платформы .NET Framework](troubleshooting-dotnet-framework-targeting-errors.md)

### [Настройка сборки](customize-your-build.md)

### [Рекомендации по MSBuild](msbuild-best-practices.md)

## [Ведение журнала в MSBuild](logging-in-msbuild.md)

### [Получение журналов построения с помощью MSBuild](obtaining-build-logs-with-msbuild.md)

### [Средства ведения журнала построения](build-loggers.md)

### [Ведение журнала в многопроцессорной среде](logging-in-a-multi-processor-environment.md)

### [Написание средств ведения журнала с поддержкой многопроцессорности](writing-multi-processor-aware-loggers.md)

### [Создание средства ведения журнала переадресации](creating-forwarding-loggers.md)

## [Пошаговое руководство. Использование MSBuild](walkthrough-using-msbuild.md)

## [Пошаговое руководство. Создание файла проекта MSBuild с нуля](walkthrough-creating-an-msbuild-project-file-from-scratch.md)

## [Справочные сведения о MSBuild](msbuild-reference.md)

### [Справочные сведения о схеме файлов проектов MSBuild](msbuild-project-file-schema-reference.md)

#### [Элемент Choose (MSBuild)](choose-element-msbuild.md)

#### [Элемент Import (MSBuild)](import-element-msbuild.md)

#### [Элемент ImportGroup](importgroup-element.md)

#### [Элемент Item (MSBuild)](item-element-msbuild.md)

#### [Элемент ItemDefinitionGroup (MSBuild)](itemdefinitiongroup-element-msbuild.md)

#### [Элемент ItemGroup (MSBuild)](itemgroup-element-msbuild.md)

#### [Элемент ItemMetadata (MSBuild)](itemmetadata-element-msbuild.md)

#### [Элемент OnError (MSBuild)](onerror-element-msbuild.md)

#### [Элемент Otherwise (MSBuild)](otherwise-element-msbuild.md)

#### [Элемент Output (MSBuild)](output-element-msbuild.md)

#### [Элемент Parameter](parameter-element.md)

#### [Элемент ParameterGroup](parametergroup-element.md)

#### [Элемент Project (MSBuild)](project-element-msbuild.md)

#### [Элемент ProjectExtensions (MSBuild)](projectextensions-element-msbuild.md)

#### [Элемент Property (MSBuild)](property-element-msbuild.md)

#### [Элемент PropertyGroup (MSBuild)](propertygroup-element-msbuild.md)

#### [Элемент Target (MSBuild)](target-element-msbuild.md)

#### [Элемент Task (MSBuild)](task-element-msbuild.md)

#### [Элемент TaskBody (MSBuild)](taskbody-element-msbuild.md)

#### [Элемент UsingTask (MSBuild)](usingtask-element-msbuild.md)

#### [Элемент When (MSBuild)](when-element-msbuild.md)

### [Справочник по задачам MSBuild](msbuild-task-reference.md)

#### [Задачи MSBuild, относящиеся к Visual C++](msbuild-tasks-specific-to-visual-cpp.md)

##### [Задача BscMake](bscmake-task.md)

##### [Задача CL](cl-task.md)

##### [Задача CPPClean](cppclean-task.md)

##### [Задача LIB](lib-task.md)

##### [Связывание задачи](link-task.md)

##### [Задача MIDL](midl-task.md)

##### [Задача MT](mt-task.md)

##### [Задача RC](rc-task.md)

##### [Задача SetEnv](setenv-task.md)

##### [Задача VCMessage](vcmessage-task.md)

##### [Задача XDCMake](xdcmake-task.md)

##### [Задача XSD](xsd-task.md)

#### [Базовый класс Task](task-base-class.md)

#### [Базовый класс TaskExtension](taskextension-base-class.md)

#### [Базовый класс ToolTaskExtension](tooltaskextension-base-class.md)

#### [Задача AL (компоновщик сборок)](al-assembly-linker-task.md)

#### [Задача AspNetCompiler](aspnetcompiler-task.md)

#### [Задача AssignCulture](assignculture-task.md)

#### [Задача AssignProjectConfiguration](assignprojectconfiguration-task.md)

#### [Задача AssignTargetPath](assigntargetpath-task.md)

#### [Задача CallTarget](calltarget-task.md)

#### [Задача CombinePath](combinepath-task.md)

#### [Задача ConvertToAbsolutePath](converttoabsolutepath-task.md)

#### [Задача Copy](copy-task.md)

#### [Задача CreateCSharpManifestResourceName](createcsharpmanifestresourcename-task.md)

#### [Задача CreateItem](createitem-task.md)

#### [Задача CreateProperty](createproperty-task.md)

#### [Задача CreateVisualBasicManifestResourceName](createvisualbasicmanifestresourcename-task.md)

#### [Задача Csc](csc-task.md)

#### [Задача Delete](delete-task.md)

#### [Задача Error](error-task.md)

#### [Задача Exec](exec-task.md)

#### [Задача FindAppConfigFile](findappconfigfile-task.md)

#### [Задача FindInList](findinlist-task.md)

#### [Задача FindUnderPath](findunderpath-task.md)

#### [Задача FormatUrl](formaturl-task.md)

#### [Задача FormatVersion](formatversion-task.md)

#### [Задача GenerateApplicationManifest](generateapplicationmanifest-task.md)

#### [Задача GenerateBootstrapper](generatebootstrapper-task.md)

#### [Задача GenerateDeploymentManifest](generatedeploymentmanifest-task.md)

#### [Задача GenerateResource](generateresource-task.md)

#### [Задача GenerateTrustInfo](generatetrustinfo-task.md)

#### [Задача GetAssemblyIdentity](getassemblyidentity-task.md)

#### [Задача GetFrameworkPath](getframeworkpath-task.md)

#### [Задача GetFrameworkSdkPath](getframeworksdkpath-task.md)

#### [Задача GetReferenceAssemblyPaths](getreferenceassemblypaths-task.md)

#### [Задача LC](lc-task.md)

#### [Задача MakeDir](makedir-task.md)

#### [Задача Message](message-task.md)

#### [Задача Move](move-task.md)

#### [Задача MSBuild](msbuild-task.md)

#### [Задача ReadLinesFromFile](readlinesfromfile-task.md)

#### [Задача RegisterAssembly](registerassembly-task.md)

#### [Задача RemoveDir](removedir-task.md)

#### [Задача RemoveDuplicates](removeduplicates-task.md)

#### [Задача RequiresFramework35SP1Assembly](requiresframework35sp1assembly-task.md)

#### [Задача ResolveAssemblyReference](resolveassemblyreference-task.md)

#### [Задача ResolveComReference](resolvecomreference-task.md)

#### [Задача ResolveKeySource](resolvekeysource-task.md)

#### [Задача ResolveManifestFiles](resolvemanifestfiles-task.md)

#### [Задача ResolveNativeReference](resolvenativereference-task.md)

#### [Задача ResolveNonMSBuildProjectOutput](resolvenonmsbuildprojectoutput-task.md)

#### [Задача SGen](sgen-task.md)

#### [Задача SignFile](signfile-task.md)

#### [Задача Touch](touch-task.md)

#### [Задача UnregisterAssembly](unregisterassembly-task.md)

#### [Задача UpdateManifest](updatemanifest-task.md)

#### [Задача Vbc](vbc-task.md)

#### [Задача Warning](warning-task.md)

#### [Задача WriteCodeFragment](writecodefragment-task.md)

#### [Задача WriteLinesToFile](writelinestofile-task.md)

#### [Задача XmlPeek](xmlpeek-task.md)

#### [Задача XmlPoke](xmlpoke-task.md)

#### [Задача XslTransformation](xsltransformation-task.md)

### [Условия MSBuild](msbuild-conditions.md)

### [Условные конструкции MSBuild](msbuild-conditional-constructs.md)

### [Зарезервированные и стандартные свойства MSBuild](msbuild-reserved-and-well-known-properties.md)

### [Общие свойства проектов MSBuild](common-msbuild-project-properties.md)

### [Общие элементы проектов MSBuild](common-msbuild-project-items.md)

### [Справочник по командной строке MSBuild](msbuild-command-line-reference.md)

### [Файлы TARGETS в MSBuild](msbuild-dot-targets-files.md)

### [Общеизвестные метаданные элементов MSBuild](msbuild-well-known-item-metadata.md)

### [Файлы ответов MSBuild](msbuild-response-files.md)

### [Справочные сведения о WPF для MSBuild](wpf-msbuild-reference.md)

#### [TARGETS-файлы WPF](wpf-dot-targets-files.md)

#### [Справочные сведения о задачах WPF для MSBuild](wpf-msbuild-task-reference.md)

##### [Задача FileClassifier](fileclassifier-task.md)

##### [Задача GenerateTemporaryTargetAssembly](generatetemporarytargetassembly-task.md)

##### [Задача GetWinFXPath](getwinfxpath-task.md)

##### [Задача MarkupCompilePass1](markupcompilepass1-task.md)

##### [Задача MarkupCompilePass2](markupcompilepass2-task.md)

##### [Задача MergeLocalizationDirectives](mergelocalizationdirectives-task.md)

##### [Задача ResourcesGenerator](resourcesgenerator-task.md)

##### [Задача UidManager](uidmanager-task.md)

##### [Задача UpdateManifestForBrowserApplication](updatemanifestforbrowserapplication-task.md)

### [Знаки, требующие отключения их специального значения](special-characters-to-escape.md)

## [Глоссарий MSBuild](msbuild-glossary.md)
