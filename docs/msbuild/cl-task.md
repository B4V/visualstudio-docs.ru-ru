---
title: "Задача CL | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
- vc.task.cl
- VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild (Visual C++), CL task
- CL task (MSBuild (Visual C++))
ms.assetid: 651ba971-b755-4f03-a549-4816beb3cc0d
caps.latest.revision: 18
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
ms.openlocfilehash: bde2b08fb3cc1b183d224ab3282e44f21a094403
ms.lasthandoff: 04/05/2017

---
# <a name="cl-task"></a>Задача CL
Использует оболочку компилятора Visual C++ — cl.exe. Компилятор создает исполняемые файлы (EXE-файлы), библиотеки динамической компоновки (DLL-файлы) или модули кода (NETMODULE-файлы). Дополнительные сведения см. в разделе [Параметры компилятора](/cpp/build/reference/compiler-options).  
  
## <a name="parameters"></a>Параметры  
 В следующей таблице приводятся параметры задачи **CL**. Большинство параметров задачи и некоторые наборы параметров соответствуют параметрам командной строки.  
  
-   **AdditionalIncludeDirectories**  
  
     Необязательный параметр String[].  
  
     Добавляет каталог к списку каталогов, в которых выполняется поиск включаемых файлов.  
  
     Дополнительные сведения см. в разделе [/I (дополнительные каталоги включения)](/cpp/build/reference/i-additional-include-directories).  
  
-   **AdditionalOptions**  
  
     Необязательный параметр String.  
  
     Список параметров командной строки. Например, "/*параметр_1* /*параметр_2* /*параметр_#*". Этот параметр используется для указания параметров командной строки, не представленных каким-либо другим параметром задачи.  
  
     Дополнительные сведения см. в разделе [Параметры компилятора](/cpp/build/reference/compiler-options).  
  
-   **AdditionalUsingDirectories**Необязательный параметр String[].  
  
     Указывает каталог, в котором компилятор будет производить поиск для разрешения ссылок, переданных в директиву **#using**.  
  
     Дополнительные сведения см. в разделе [/AI (указание каталогов метаданных)](/cpp/build/reference/ai-specify-metadata-directories).  
  
-   **AlwaysAppend**  
  
     Необязательный параметр String.  
  
     Строка, которая всегда выводится в командной строке. Значение по умолчанию — "**/c**".  
  
-   **AssemblerListingLocation**  
  
     Создает файл листинга, содержащий код сборки.  
  
     Дополнительные сведения см. в описании параметра **/Fa** в разделе [/FA, /Fa (файл листинга)](/cpp/build/reference/fa-fa-listing-file).  
  
-   **AssemblerOutput**  
  
     Необязательный параметр String.  
  
     Создает файл листинга, содержащий код сборки.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **NoListing** - *\<отсутствует>*  
  
    -   **AssemblyCode** - **/FA**  
  
    -   **AssemblyAndMachineCode** - **/FAc**  
  
    -   **AssemblyAndSourceCode** - **/FAs**  
  
    -   **All** - **/FAcs**  
  
     Дополнительные сведения см. в описании параметров **/FA**, **/FAc**, **/FAs** и **/FAcs** в разделе [/FA, /Fa (файл листинга)](/cpp/build/reference/fa-fa-listing-file).  
  
-   **BasicRuntimeChecks**  
  
     Необязательный параметр String.  
  
     Включает и отключает функцию проверки ошибок во время выполнения совместно с атрибутом директивы pragma [runtime_checks](/cpp/preprocessor/runtime-checks).  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **Default** -                          *\<отсутствует>*  
  
    -   **StackFrameRuntimeCheck** - **/RTCs**  
  
    -   **UninitializedLocalUsageCheck** - **/RTCu**  
  
    -   **EnableFastChecks** -                          **/RTC1**  
  
     Дополнительные сведения см. в разделе [/RTC (проверки ошибок во время выполнения)](/cpp/build/reference/rtc-run-time-error-checks).  
  
-   **BrowseInformation**  
  
     Необязательный логический параметр.  
  
     Если он имеет значение `true`, создается файл информации об исходном коде.  
  
     Дополнительные сведения см. в описании параметра **/FR** в разделе [/FR, /Fr (создать SBR-файл)](/cpp/build/reference/fr-fr-create-dot-sbr-file).  
  
-   **BrowseInformationFile**  
  
     Необязательный параметр String.  
  
     Задает имя для файла информации об исходном коде.  
  
     Дополнительные сведения см. в описании параметра **BrowseInformation** в этой таблице, а также в разделе [/FR, /Fr (создать SBR-файл)](/cpp/build/reference/fr-fr-create-dot-sbr-file).  
  
-   **BufferSecurityCheck**  
  
     Необязательный логический параметр.  
  
     Если значение равно `true`, обнаруживаются некоторые переполнения буфера, при которых перезаписывается обратный адрес. Это стандартный способ работы с кодом, в котором не используется принудительное ограничение размера буфера.  
  
     Дополнительные сведения см. в разделе [Параметр /GS (проверка безопасности буфера)](/cpp/build/reference/gs-buffer-security-check).  
  
-   **BuildingInIDE**  
  
     Необязательный логический параметр.  
  
     Если он имеет значение `true`, то указывает, что **MSBuild** вызывается средой IDE. В противном случае **MSBuild** вызывается в командной строке.  
  
-   **CallingConvention**  
  
     Необязательный параметр String.  
  
     Задает соглашение о вызове, определяющее порядок, в котором аргументы функции передаются в стек, то, удаляет ли вызывающая или вызываемая функция аргументы из стека в конце вызова, а также соглашение о декорировании имен, используемое компилятором для идентификации отдельных функций.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **Cdecl** - **/Gd**  
  
    -   **FastCall** -                          **/Gr**  
  
    -   **StdCall** -                          **/Gz**  
  
     Дополнительные сведения см. в разделе [/Gd, /Gr, /Gv, /Gz (соглашение о вызовах)](/cpp/build/reference/gd-gr-gv-gz-calling-convention).  
  
-   **CompileAs**  
  
     Необязательный параметр String.  
  
     Указывает, должен ли входной файл компилироваться как исходный файл C или C++.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **Default** - *\<отсутствует>*  
  
    -   **CompileAsC** - **/TC**  
  
    -   **CompileAsCpp** - **/TP**  
  
     Дополнительные сведения см. в разделе [Параметры /Tc, /Tp, /TC, /TP (определение типа исходного файла)](/cpp/build/reference/tc-tp-tc-tp-specify-source-file-type).  
  
-   **CompileAsManaged**  
  
     Необязательный параметр String.  
  
     Позволяет приложениям и компонентам использовать возможности из среды CLR.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **false** - *\<отсутствует>*  
  
    -   **true** - **/clr**  
  
    -   **Pure** - **/clr:pure**  
  
    -   **Safe** - **/clr:safe**  
  
    -   **OldSyntax** - **/clr:oldSyntax**  
  
     Дополнительные сведения см. в разделе [/clr (компиляция CLR)](/cpp/build/reference/clr-common-language-runtime-compilation).  
  
-   **CreateHotpatchableImage**  
  
     Необязательный логический параметр.  
  
     Если он имеет значение `true`, то компилятор должен подготовить образ для *критического обновления*. Этот параметр позволяет добиться того, что длина первой инструкции каждой функции равна двум байтам, что необходимо для выполнения критического обновления.  
  
     Дополнительные сведения см. в разделе [/hotpatch (создать образ с обновлениями)](/cpp/build/reference/hotpatch-create-hotpatchable-image).  
  
-   **DebugInformationFormat**  
  
     Необязательный параметр String.  
  
     Выбирает тип отладочной информации, создаваемой для программы, и место хранения этой информации: объектные файлы (OBJ) или база данных программы (PDB).  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **OldStyle** - **/Z7**  
  
    -   **ProgramDatabase** - **/Zi**  
  
    -   **EditAndContinue** - **/ZI**  
  
     Дополнительные сведения см. в разделе [/Z7, /Zi, /ZI (формат отладочной информации)](/cpp/build/reference/z7-zi-zi-debug-information-format).  
  
-   **DisableLanguageExtensions**  
  
     Необязательный логический параметр.  
  
     Если он имеет значение **true**, то компилятор должен выдавать ошибку для языковых конструкций, несовместимых либо с ANSI C, либо с ANSI C++.  
  
     Дополнительные сведения см. в описании параметра **/Za** в разделе [/Za, /Ze (отключить расширения языка)](/cpp/build/reference/za-ze-disable-language-extensions).  
  
-   **DisableSpecificWarnings**  
  
     Необязательный параметр String[].  
  
     Отключает номера предупреждений, которые указаны в списке, разделенном точками с запятой.  
  
     Дополнительные сведения см. в описании параметра `/wd` в разделе [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (уровень предупреждений)](/cpp/build/reference/compiler-option-warning-level).  
  
-   **EnableEnhancedInstructionSet**  
  
     Необязательный параметр String.  
  
     Этот параметр задает архитектуру для создания кода с помощью наборов инструкций Streaming SIMD Extensions (SSE) и Streaming SIMD Extensions 2 (SSE2).  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **StreamingSIMDExtensions** - **/arch:SSE**  
  
    -   **StreamingSIMDExtensions2** - **/arch:SSE2**  
  
     Дополнительные сведения см. в разделе [/arch (x86)](/cpp/build/reference/arch-x86).  
  
-   **EnableFiberSafeOptimizations**  
  
     Необязательный логический параметр.  
  
     Если он имеет значение `true`, то поддерживается безопасность волокон для данных, выделенных с помощью статической локальной памяти потока, то есть данных, выделенных с помощью `__declspec(thread)`.  
  
     Дополнительные сведения см. в разделе [/GT (поддержка локальной памяти потока, безопасной относительно волокон)](/cpp/build/reference/gt-support-fiber-safe-thread-local-storage).  
  
-   **EnablePREfast**  
  
     Необязательный логический параметр.  
  
     Если он имеет значение `true`, то включается анализ кода.  
  
     Дополнительные сведения см. в разделе [/analyze (анализ кода)](/cpp/build/reference/analyze-code-analysis).  
  
-   **ErrorReporting**  
  
     Необязательный параметр String.  
  
     Разрешает передавать данные о внутренних ошибках компилятора (ICE) непосредственно в корпорацию Майкрософт. По умолчанию в сборках среды IDE этот параметр имеет значение **Prompt**, а в сборках командной строки — значение **Queue**.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **None** - **/errorReport:none**  
  
    -   **Prompt** - **/errorReport:prompt**  
  
    -   **Queue** - **/errorReport:queue**  
  
    -   **Send** - **/errorReport:send**  
  
     Дополнительные сведения см. в разделе [Параметр /errorReport (отчет о внутренних ошибках компилятора)](/cpp/build/reference/errorreport-report-internal-compiler-errors).  
  
-   **ExceptionHandling**  
  
     Необязательный параметр String.  
  
     Задает модель обработки исключений, используемую компилятором.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **false** - *\<отсутствует>*  
  
    -   **Async** - **/EHa**  
  
    -   **Sync** - **/EHsc**  
  
    -   **SyncCThrow** - **/EHs**  
  
     Дополнительные сведения см. в статье [/EH (модель обработки исключений)](/cpp/build/reference/eh-exception-handling-model).  
  
-   **ExpandAttributedSource**  
  
     Необязательный логический параметр.  
  
     Если он имеет значение `true`, то создается файл списка, имеющий расширенные атрибуты, внедренные в исходный файл.  
  
     Дополнительные сведения см. в разделе [/Fx (слияние подставляемого кода)](/cpp/build/reference/fx-merge-injected-code) .  
  
-   **FavorSizeOrSpeed**  
  
     Необязательный параметр String.  
  
     Указывает, нужно ли предпочитать скорость или размер кода.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **Neither** - *\<отсутствует>*  
  
    -   **Size** - **/Os**  
  
    -   **Speed** - **/Ot**  
  
     Дополнительные сведения см. в разделе [/Os, /Ot (приоритет размера кода или скорости кода)](/cpp/build/reference/os-ot-favor-small-code-favor-fast-code).  
  
-   **FloatingPointExceptions**  
  
     Необязательный логический параметр.  
  
     Если он имеет значение `true`, то включается надежная модель исключения с плавающей запятой. Исключения вызываются сразу же после их инициализации.  
  
     Дополнительные сведения см. в описании параметра /**fp:except** в разделе [/fp (Определение поведения с плавающей запятой)](/cpp/build/reference/fp-specify-floating-point-behavior).  
  
-   **FloatingPointModel**  
  
     Необязательный параметр String.  
  
     Задает модель с плавающей запятой.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **Precise** - **/fp:precise**  
  
    -   **Strict** - **/fp:strict**  
  
    -   **Fast** - **/fp:fast**  
  
     Дополнительные сведения см. в разделе [/fp (определение поведения с плавающей запятой)](/cpp/build/reference/fp-specify-floating-point-behavior).  
  
-   **ForceConformanceInForLoopScope**  
  
     Необязательный логический параметр.  
  
     Если он имеет значение `true`, то реализуется стандартное поведение C++ в для циклов [for](/cpp/cpp/for-statement-cpp), использующих расширения Майкрософт ([/Ze](/cpp/build/reference/za-ze-disable-language-extensions)).  
  
     Дополнительные сведения см. в разделе [/Zc:forScope (принудительное обеспечение соответствия в области видимости оператора for)](http://msdn.microsoft.com/Library/3031f02d-3b14-4ad0-869e-22b0110c3aed).  
  
-   **ForcedIncludeFiles**  
  
     Необязательный параметр `String[]` .  
  
     Вызывает обработку препроцессором одного или нескольких указанных файлов заголовков.  
  
     Дополнительные сведения см. в разделе [/FI (имя принудительно включаемого файла)](/cpp/build/reference/fi-name-forced-include-file).  
  
-   **ForcedUsingFiles**  
  
     Необязательный параметр типа **String[]**.  
  
     Вызывает обработку препроцессором одного или нескольких указанных файлов **#using**.  
  
     Дополнительные сведения см. в разделе [/FU (именование файла с принудительно используемым атрибутом #using)](/cpp/build/reference/fu-name-forced-hash-using-file).  
  
-   **FunctionLevelLinking**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, компилятор может упаковывать отдельные функции в форме упакованных функций (COMDAT).  
  
     Дополнительные сведения см. в разделе [/Gy (включение компоновки на уровне функций)](/cpp/build/reference/gy-enable-function-level-linking).  
  
-   **GenerateXMLDocumentationFiles**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, компилятор обрабатывает комментарии к документации в файлах исходного кода и создает XDC-файл для каждого файла с исходным кодом, в котором есть комментарии к документации.  
  
     Дополнительные сведения см. в разделе [/doc (обработка комментариев документации) (C/C++)](/cpp/build/reference/doc-process-documentation-comments-c-cpp). См. также описание параметра **XMLDocumentationFileName** в этой таблице.  
  
-   **IgnoreStandardIncludePath**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, компилятор не выполняет поиск файлов для включения в каталогах, указанных в переменных среды PATH и INCLUDE.  
  
     Дополнительные сведения см. в разделе [/X (отклонение стандартных путей включения)](/cpp/build/reference/x-ignore-standard-include-paths).  
  
-   **InlineFunctionExpansion**  
  
     Необязательный параметр типа **String**.  
  
     Задает уровень расширения встраиваемых функций для сборки.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **Default** - *\<отсутствует>*  
  
    -   **Disabled** - **/Ob0**  
  
    -   **OnlyExplicitInline** - **/Ob1**  
  
    -   **AnySuitable** - **/Ob2**  
  
     Дополнительные сведения см. в разделе [Параметр /Ob (расширение встраиваемых функций)](/cpp/build/reference/ob-inline-function-expansion).  
  
-   **IntrinsicFunctions**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, вызов некоторых функций заменяется на встроенные или какие-либо другие формы функции, которые способствуют более быстрому выполнению приложения.  
  
     Дополнительные сведения см. в разделе [/Oi (создание встроенных функций)](/cpp/build/reference/oi-generate-intrinsic-functions).  
  
-   **MinimalRebuild**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, включается минимальное перестроение, определяющее, необходимо ли перекомпилировать исходные файлы C++, содержащие измененные определения классов C++ (хранящиеся в файлах заголовка (H)).  
  
     Дополнительные сведения см. в разделе [/Gm (включение минимального перепостроения)](/cpp/build/reference/gm-enable-minimal-rebuild).  
  
-   **MultiProcessorCompilation**  
  
     Необязательный параметр `Boolean` .  
  
     Если он имеет значение `true`, то для компиляции используется несколько процессоров. Этот параметр создает процесс для каждого эффективного процессора на компьютере.  
  
     Дополнительные сведения см. в разделе [/MP (построить с несколькими процессами)](/cpp/build/reference/mp-build-with-multiple-processes). См. также описание параметра **ProcessorNumber** в этой таблице.  
  
-   **ObjectFileName**  
  
     Необязательный параметр типа **String**.  
  
     Указывает имя файла или каталога объектного файла (OBJ), которое следует использовать вместо имени по умолчанию.  
  
     Дополнительные сведения см. в разделе [/Fo (имя объектного файла)](/cpp/build/reference/fo-object-file-name).  
  
-   **ObjectFiles**  
  
     Необязательный параметр типа **String[]**.  
  
     Список объектных файлов.  
  
-   **OmitDefaultLibName**  
  
     Необязательный параметр `Boolean` .  
  
     Если он имеет значение `true`, то имя библиотеки времени выполнения С, установленное по умолчанию, опускается в объектном файле (OBJ-файле). По умолчанию компилятор помещает имя библиотеки в OBJ-файл, чтобы перенаправить компоновщик в правильную библиотеку.  
  
     Дополнительные сведения см. в разделе [/Zl (опущенное по умолчанию имя библиотеки)](/cpp/build/reference/zl-omit-default-library-name).  
  
-   **OmitFramePointers**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, подавляется создание указателей фрейма в стеке вызова.  
  
     Дополнительные сведения см. в разделе [/Oy (подавление указателей фрейма)](/cpp/build/reference/oy-frame-pointer-omission).  
  
-   **OpenMPSupport**  
  
     Необязательный параметр `Boolean` .  
  
     Если он имеет значение `true`, то компилятор будет обрабатывать предложения и директивы OpenMP.  
  
     Дополнительные сведения см. в разделе [/openmp (включение поддержки OpenMP 2.0)](/cpp/build/reference/openmp-enable-openmp-2-0-support).  
  
-   **Optimization**  
  
     Необязательный параметр типа **String**.  
  
     Задает различные оптимизации скорости и размера кода.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **Disabled** - **/Od**  
  
    -   **MinSpace** - **/O1**  
  
    -   **MaxSpeed** - **/O2**  
  
    -   **Full** - **/Ox**  
  
     Дополнительные сведения см. в разделе [Параметры /O (оптимизация кода)](/cpp/build/reference/o-options-optimize-code).  
  
-   **PrecompiledHeader**  
  
     Необязательный параметр типа **String**.  
  
     Создание или использование файла предкомпилированного заголовка (PCH-файла) во время сборки.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **NotUsing** - *\<отсутствует>*  
  
    -   **Create** - **/Yc**  
  
    -   **Use** - **/Yu**  
  
     Дополнительные сведения см. в разделах [/Yc (создать предкомпилированный заголовочный файл)](/cpp/build/reference/yc-create-precompiled-header-file) и [/Yu (использование файла предкомпилированного заголовка)](/cpp/build/reference/yu-use-precompiled-header-file). Кроме того, см. параметры **PrecompiledHeaderFile** и **PrecompiledHeaderOutputFile** в этой таблице.  
  
-   **PrecompiledHeaderFile**  
  
     Необязательный параметр типа **String**.  
  
     Задает имя файла предкомпилированного заголовка для создания или использования.  
  
     Дополнительные сведения см. в разделах [/Yc (создать предкомпилированный заголовочный файл)](/cpp/build/reference/yc-create-precompiled-header-file) и [/Yu (использование файла предкомпилированного заголовка)](/cpp/build/reference/yu-use-precompiled-header-file).  
  
-   **PrecompiledHeaderOutputFile**  
  
     Необязательный параметр типа **String**.  
  
     Задает путь для предкомпилированного заголовка, который используется вместо пути по умолчанию.  
  
     Дополнительные сведения см. в разделе [/Fp (имя PCH-файла)](/cpp/build/reference/fp-name-dot-pch-file).  
  
-   **PreprocessKeepComments**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, в ходе предварительной обработки комментарии сохраняются.  
  
     Дополнительные сведения см. в разделе [/C (сохранять комментарии во время предварительной обработки)](/cpp/build/reference/c-preserve-comments-during-preprocessing).  
  
-   **PreprocessorDefinitions**  
  
     Необязательный параметр `String[]` .  
  
     Определяет символ предобработки для исходного файла.  
  
     Для получения дополнительной информации см. раздел [Определения препроцессора (/D)](/cpp/build/reference/d-preprocessor-definitions).  
  
-   **PreprocessOutput**  
  
     Необязательный параметр `ITaskItem[]`.  
  
     Определяет массив выходных элементов препроцессора, которые могут использоваться и создаваться задачами.  
  
-   **PreprocessOutputPath**  
  
     Необязательный параметр `String` .  
  
     Задает имя выходного файла, в который параметр **PreprocessToFile** записывает предварительно обработанные выходные данные.  
  
     Дополнительные сведения см. в разделе [/Fi (предварительная обработка имени выходного файла)](/cpp/build/reference/fi-preprocess-output-file-name).  
  
-   **PreprocessSuppressLineNumbers**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, выполняется предобработка исходных файлов C и C++, которые копируются на стандартное устройство вывода.  
  
     Дополнительные сведения см. в разделе [/EP (предварительная обработка в поток стандартных выходных файлов без директив #line)](/cpp/build/reference/ep-preprocess-to-stdout-without-hash-line-directives).  
  
-   **PreprocessToFile**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, выполняется предобработка файлов на языке C и С++, а выходные данные записываются в файл.  
  
     Дополнительные сведения см. в разделе [/P (вывод результатов предварительной обработки в файл)](/cpp/build/reference/p-preprocess-to-a-file).  
  
-   **ProcessorNumber**  
  
     Необязательный параметр `Integer`.  
  
     Задает максимальное число процессоров, которые могут использоваться в многопроцессорной компиляции. Используйте этот параметр вместе с параметром **MultiProcessorCompilation**.  
  
-   **ProgramDataBaseFileName**  
  
     Необязательный параметр `String` .  
  
     Задает имя файла для базы данных программы (PDB-файла).  
  
     Дополнительные сведения см. в разделе [/Fd (имя файла базы данных программы)](/cpp/build/reference/fd-program-database-file-name).  
  
-   **RuntimeLibrary**  
  
     Необязательный параметр `String` .  
  
     Указывает, является ли многопотоковый модуль библиотекой DLL, и выбирает версию библиотеки времени выполнения для отладки или выпуска.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **MultiThreaded** - **/MT**  
  
    -   **MultiThreadedDebug** - **/MTd**  
  
    -   **MultiThreadedDLL** - **/MD**  
  
    -   **MultiThreadedDebugDLL** - **/MDd**  
  
     Дополнительные сведения см. в разделе [/MD, /MT, /LD (использование библиотеки времени выполнения)](/cpp/build/reference/md-mt-ld-use-run-time-library).  
  
-   **RuntimeTypeInfo**  
  
     Необязательный параметр `Boolean` .  
  
     Если он имеет значение `true`, то добавляется код для проверки типов объектов C++ во время выполнения (сведения о типе времени выполнения).  
  
     Дополнительные сведения см. в разделе [/GR (предоставление информации о типах во время выполнения)](/cpp/build/reference/gr-enable-run-time-type-information).  
  
-   **ShowIncludes**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, компилятор выводит список включаемых файлов.  
  
     Дополнительные сведения см. в разделе [/showIncludes (список включаемых файлов)](/cpp/build/reference/showincludes-list-include-files).  
  
-   **SmallerTypeCheck**  
  
     Необязательный параметр `Boolean` .  
  
     Если он имеет значение `true`, то выводится сообщение об ошибке времени выполнения, когда значение назначается типу данных меньшего размера, что приводит к потере данных.  
  
     Дополнительные сведения см. в описании параметра **/RTCc** в разделе [/RTC (проверки ошибок во время выполнения)](/cpp/build/reference/rtc-run-time-error-checks).  
  
-   **Sources**  
  
     Обязательный параметр `ITaskItem[]`.  
  
     Задает список исходных файлов, разделенных пробелами.  
  
-   **StringPooling**  
  
     Необязательный параметр `Boolean` .  
  
     Если он имеет значение `true`, то компилятору позволено создавать одну копию одинаковых строк в образе программы.  
  
     Дополнительные сведения см. в разделе [/GF (исключение повторяющихся строк)](/cpp/build/reference/gf-eliminate-duplicate-strings).  
  
-   **StructMemberAlignment**  
  
     Необязательный параметр `String` .  
  
     Задает байтовое выравнивание для всех элементов в структуре.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **Default** - **/Zp1**  
  
    -   **1Byte** - **/Zp1**  
  
    -   **2Bytes** - **/Zp2**  
  
    -   **4Bytes** - **/Zp4**  
  
    -   **8Bytes** - **/Zp8**  
  
    -   **16Bytes** - **/Zp16**  
  
     Дополнительные сведения см. в статье [/Zp (выравнивание членов структур)](/cpp/build/reference/zp-struct-member-alignment).  
  
-   **SuppressStartupBanner**  
  
     Необязательный параметр `Boolean` .  
  
     Если задано значение `true`, запрещается отображение сообщения о номере версии и авторских правах при запуске задачи.  
  
     Дополнительные сведения см. в разделе [/nologo (отмена вывода начального заголовка) (C/C++)](/cpp/build/reference/nologo-suppress-startup-banner-c-cpp).  
  
-   **TrackerLogDirectory**  
  
     Необязательный параметр `String` .  
  
     Задает промежуточный каталог, в котором хранятся журналы отслеживания для этой задачи.  
  
     Дополнительные сведения см. в описании параметров **TLogReadFiles** и **TLogWriteFiles** в этой таблице.  
  
-   **TreatSpecificWarningsAsErrors**  
  
     Необязательный параметр типа **String[]**.  
  
     Обрабатывает указанный список предупреждений компилятора как ошибки.  
  
     Дополнительные сведения см. в описании параметра **/we**`n` в разделе [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (уровень предупреждений)](/cpp/build/reference/compiler-option-warning-level).  
  
-   **TreatWarningAsError**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, все предупреждения компилятора обрабатываются как ошибки.  
  
     Дополнительные сведения см. в описании параметра **/WX** в разделе [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (уровень предупреждений)](/cpp/build/reference/compiler-option-warning-level).  
  
-   **TreatWChar_tAsBuiltInType**  
  
     Необязательный параметр `Boolean` .  
  
     Если он имеет значение `true`, то тип `wchar_t` трактуется как собственный тип.  
  
     Дополнительные сведения см. в разделе [/Zc:wchar_t (wchar_t — это собственный тип)](http://msdn.microsoft.com/Library/b0de5a84-da72-4e5a-9a4e-541099f939e0).  
  
-   **UndefineAllPreprocessorDefinitions**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, отменяется определение символов для систем Майкрософт, определяемых компилятором.  
  
     Дополнительные сведения см. в описании параметра **/u** в разделе [Параметры /U и /u (отмена определения символа)](/cpp/build/reference/u-u-undefine-symbols).  
  
-   **UndefinePreprocessorDefinitions**  
  
     Необязательный параметр `String[]` .  
  
     Задает список одного или нескольких символов препроцессора для отмены определения.  
  
     Дополнительные сведения см. в описании параметра **/U** в разделе [Параметры /U и /u (отмена определения символа)](/cpp/build/reference/u-u-undefine-symbols).  
  
-   **UseFullPaths**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, отображается полный путь к файлам исходного кода, переданный компилятору в диагностике.  
  
     Дополнительные сведения см. в разделе [/FC (полный путь к файлу исходного кода в папке Diagnostics)](/cpp/build/reference/fc-full-path-of-source-code-file-in-diagnostics).  
  
-   **UseUnicodeForAssemblerListing**  
  
     Необязательный параметр `Boolean` .  
  
     Если он имеет значение `true`, то выходной файл будет создан в формате UTF-8.  
  
     Дополнительные сведения см. в описании параметра **/FAu** в разделе [/FA, /Fa (файл листинга)](/cpp/build/reference/fa-fa-listing-file).  
  
-   **WarningLevel**  
  
     Необязательный параметр `String` .  
  
     Задает высший уровень предупреждений, создаваемых компилятором.  
  
     Укажите одно из следующих значений, каждое из которых соответствует параметру командной строки.  
  
    -   **TurnOffAllWarnings** - **/W0**  
  
    -   **Level1** - **/W1**  
  
    -   **Level2** - **/W2**  
  
    -   **Level3** - **/W3**  
  
    -   **Level4** - **/W4**  
  
    -   **EnableAllWarnings** - **/Wall**  
  
     Дополнительные сведения см. в описании параметра **/W***n* в разделе [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (уровень предупреждений)](/cpp/build/reference/compiler-option-warning-level).  
  
-   **WholeProgramOptimization**  
  
     Необязательный параметр `Boolean` .  
  
     Если значение равно `true`, включается оптимизация всей программы.  
  
     Дополнительные сведения см. в разделе [/GL (оптимизация всей программы)](/cpp/build/reference/gl-whole-program-optimization).  
  
-   **XMLDocumentationFileName**  
  
     Необязательный параметр `String` .  
  
     Задает имя создаваемых XML-файлов документации. Этот параметр может быть именем файла или каталога.  
  
     Дополнительные сведения см. описание аргумента `name` в разделе [/doc (обработка комментариев документации) (C/C++)](/cpp/build/reference/doc-process-documentation-comments-c-cpp). См. также описание параметра **GenerateXMLDocumentationFiles** в этой таблице.  
  
-   **MinimalRebuildFromTracking**  
  
     Необязательный параметр `Boolean` .  
  
     Если он имеет значение `true`, то выполняется отслеживаемая инкрементная сборка; если значение `false`, то выполняется перестроение.  
  
-   **TLogReadFiles**  
  
     Необязательный параметр `ITaskItem[]`.  
  
     Определяет массив элементов, представляющих *журналы отслеживания чтения из файла*.  
  
     Журнал отслеживания чтения из файла (TLOG) содержит имена входных файлов, прочитанных задачей, и используется в системе сборки проекта для поддержки инкрементных сборок. Дополнительные сведения см. в описании параметров **TrackerLogDirectory** и **TrackFileAccess** в этой таблице.  
  
-   **TLogWriteFiles**  
  
     Необязательный параметр `ITaskItem[]`.  
  
     Определяет массив элементов, представляющих *журналы отслеживания записи в файл*.  
  
     Журнал отслеживания записи в файл (TLOG) содержит имена выходных файлов, записанных задачей, и используется в системе сборки проекта для поддержки инкрементных сборок. Дополнительные сведения см. в описании параметров **TrackerLogDirectory** и **TrackFileAccess** в этой таблице.  
  
-   **TrackFileAccess**  
  
     Необязательный параметр `Boolean` .  
  
     Если он имеет значение `true`, то выполняется отслеживание шаблонов доступа к файлу.  
  
     Дополнительные сведения см. в описании параметров **TLogReadFiles** и **TLogWriteFiles** в этой таблице.  
  
## <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)