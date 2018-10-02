---
title: Страница "Параметры", свойства узла отладки | Документы Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 564cc8b2-0084-420e-b560-200cc5621a7e
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 128e4719775a4ce9d06214547936110ed88b7a14
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47558175"
---
# <a name="options-page-debugging-node-properties"></a>Страница "Параметры", свойства узла отладки
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [страница "Параметры", свойства узла отладки](https://docs.microsoft.com/visualstudio/ide/reference/options-page-debugging-node-properties).  
  
  
В следующих таблицах описываются некоторые из страниц (или коллекций свойств), связанных с категорией **отладки** — `DTE.Properties("Debugging", <Property Page>)` — диалогового окна **Параметры**.  
  
## <a name="general"></a>Общие  
 `DTE.Properties("Debugging", "General")`  
  
|Имя элемента свойства|Значение|Описание|  
|------------------------|-----------|-----------------|  
|PromptOnBreakpointDelete|Get/Set (Boolean)|Определяет, запрашивает ли отладчик разрешение перед удалением всех точек останова в проекте.|  
|BreakAllProcesses|Get/Set (Boolean)|Определяет, прерывает ли отладчик все процессы при прекращении одного процесса.|  
|BreakAtBoundaries|Get/Set (Boolean)|Определяет, прерывает ли отладчик выполнение, если исключение переходит границу между доменами приложения или границу между управляемым и машинным кодом.|  
|EnableAddressLevelDebugging|Get/Set (Boolean)|Определяет, включены ли функции отладки на уровне адреса.|  
|ShowDisassemblyIfNoSource|Get/Set (Boolean)|Определяет, отображает ли отладчик отображает дизассемблированный код, если исходный код недоступен.|  
|EnableBreakpointFilters|Get/Set (Boolean)|Определяет, включена ли фильтрация точек останова.|  
|EnableExceptionAssistant|Get/Set (Boolean)|Определяет, используется ли помощник по исключениям для управляемых исключений.|  
|UnwindCallstack|Get/Set (Boolean)|Определяет, очищает ли отладчик стек вызовов для необработанных исключений.|  
|EnableJustMyCode|Get/Set (Boolean)|Определяет, включена ли функция "Только мой код" для кода C# и Visual Basic.|  
|ShowAllMembers|Get/Set (Boolean)|Для объектов, не являющихся пользователями, определяет, отображает ли отладчик все элементы объектов в окнах переменных. Этот параметр не оказывает никакого влияния, если только не включена функция "Только мой код".|  
|WarnIfNoUserCode|Get/Set (Boolean)|Определяет, выдает ли отладчик предупреждение, когда пользователь пытается подключиться к процессу, который не содержит пользовательский код. Этот параметр не оказывает никакого влияния, если только не включена функция "Только мой код".|  
|EnablePropertyEvaluation|Get/Set (Boolean)|Определяет, выполняет ли отладчик автоматическое вычисление свойств и неявных вызовов функций в управляемом коде.|  
|CallStringConversion|Get/Set (Boolean)|Определяет, выполняет ли отладчик неявный вызов функции преобразования строк для объектов в окнах переменных. Этот параметр применяется только к коду C# и JScript.|  
|EnableSourceServer|Get/Set (Boolean)|Определяет, может ли отладчик получить доступа к коду с исходного сервера.|  
|PrintSourceServerDiagnostics|Get/Set (Boolean)|Определяет, отображаются ли в окне вывода диагностические сообщения, связанные с исходным сервером. Этот параметр не оказывает никакого влияния, если только не включен доступ к серверу исходного кода.|  
|HighlightEntireLine|Get/Set (Boolean)|Определяет, выделяет ли отладчик всю строку для точек останова и текущего оператора.|  
|RequireSourceToMatch|Get/Set (Boolean)|Определяет, требуется ли отладчик полного соответствия файлов исходного кода с изначальной версией при открытии файлов для отладки.|  
|RedirectOutputToImmediate|Get/Set (Boolean)|Определяет, перенаправляются ли выходные данные из окна вывода в окно интерпретации.|  
|ShowRawVariableStructure|Get/Set (Boolean)|Определяет, отображаются ли объекты в окнах переменных в необработанном виде.|  
|SuppressJitOptimization|Get/Set (Boolean)|Для управляемого кода определяет, подавляется ли JIT-оптимизация отладчиком.|  
|WarnIfNoSymbols|Get/Set (Boolean)|Определяет, отображает ли отладчик предупреждение, если при запуске процесса недоступны символы отладки.|  
|WarnIfScriptDisabled|Get/Set (Boolean)|Определяет, отображает ли отладчик предупреждение, если при запуске процесса не включена отладка скриптов.|  
|ShowMarkersForAllThreads|Get/Set (Boolean)|Определяет, отображает ли отладчик маркеры потоков.|  
|StepOverPropertiesAndOperators|Get/Set (Boolean)|Указывает, следует ли выполнять шаг с обходом по свойствам и операторам только в управляемом коде.|  
  
## <a name="edit-and-continue"></a>Изменить и продолжить  
 `DTE.Properties("Debugging", "EditAndContinue")`  
  
|Имя элемента свойства|Значение|Описание|  
|------------------------|-----------|-----------------|  
|EnableEditAndContinue|Get/Set (Boolean)|Определяет, включена ли функция "Изменить и продолжить". Этот параметр применяется для всех языков, поддерживающих функцию "Изменить и продолжить".|  
|InvokedByCommands|Get/Set (Boolean)|Определяет, применяет ли функция "Изменить и продолжить" изменения кода автоматически, когда пользователь выбирает команду отладки, такую как **Шаг** или **Продолжить**. Этот параметр применяется только к машинному коду.|  
|InvokedByCommandsAskFirst|Get/Set (Boolean)|Определяет, запрашивает ли функция "Изменить и продолжить" у пользователя разрешение на применение изменений кода, когда пользователь выбирает команду отладки, такую как **Шаг** или **Продолжить**. Этот параметр применяется только к машинному коду.|  
|WarnAboutStaleCode|Get/Set (Boolean)|Определяет, выдает ли отладчик предупреждения, если функция "Изменить и продолжить" приводит к выполнению устаревшего кода. Этот параметр применяется только к машинному коду.|  
|RelinkChangesOnStop|Get/Set (Short)|Определяет, будет ли Visual Studio повторно связывать изменения кода, примененные функцией "Изменить и продолжить" при остановке выполнения приложения. Этот параметр применяется только к машинному коду.|  
|AllowPrecompiling|Get/Set (Short)|Определяет, является разрешено ли функции "Изменить и продолжить" загружать предкомпилированные заголовки в фоновом режиме. Этот параметр применяется только к машинному коду.|  
  
## <a name="just-in-time"></a>JIT  
 `DTE.Properties("Debugging", "JustInTime")`  
  
|Имя элемента свойства|Значение|Описание|  
|------------------------|-----------|-----------------|  
|JitManaged|Get/Set (Boolean)|Определяет, включена ли JIT-отладка для управляемого кода.|  
|JitNative|Get/Set (Boolean)|Определяет, включена ли JIT-отладка для машинного кода.|  
|JitScript|Get/Set (Boolean)|Определяет, включена ли JIT-отладка для кода скриптов.|  
  
## <a name="native"></a>машинный код;  
 `DTE.Properties("Debugging", "Native")`  
  
|Имя элемента свойства|Значение|Описание|  
|------------------------|-----------|-----------------|  
|LoadDllExports|Get/Set (Boolean)|Определяет, загружает ли отладчик таблицы экспорта библиотеки DLL.|  
|EnableRPC|Get/Set (Boolean)|Определяет, может ли отладчик войти в удаленные вызовы процедур COM.|  
  
## <a name="see-also"></a>См. также  
 [Управление параметрами](http://msdn.microsoft.com/library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [Определение имен элементов свойств на страницах параметров](http://msdn.microsoft.com/library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [Страница "Параметры", свойства узла "Шрифты и цвета"](../../ide/reference/options-page-fonts-and-colors-node-properties.md)   
 [Страница "Параметры", свойства узла "Текстовый редактор"](../../ide/reference/options-page-text-editor-node-properties.md)   
 [Страница "Общие", папка "Отладка", диалоговое окно "Параметры"](../../debugger/general-debugging-options-dialog-box.md)   
 [Страница "Изменить и продолжить", папка "Отладка", диалоговое окно "Параметры"](http://msdn.microsoft.com/library/009d225f-ef65-463f-a146-e4c518f86103)   
 [Страница "JIT-отладка", папка "Отладка", диалоговое окно "Параметры"](../../debugger/just-in-time-debugging-options-dialog-box.md)


