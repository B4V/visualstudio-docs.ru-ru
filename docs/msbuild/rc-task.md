---
title: "Задача RC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions"
  - "vc.task.rc"
  - "VC.Project.VCResourceCompilerTool.SuppressStartupBanner"
  - "VC.Project.VCResourceCompilerTool.NullTerminateStrings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
  - "C++"
helpviewer_keywords: 
  - "MSBuild (Visual C++), RC - задача"
  - "RC - задача (MSBuild (Visual C++))"
ms.assetid: 2fd26c75-a056-4dda-9f7e-2f90d3748d88
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# Задача RC
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Создает оболочку компилятора ресурсов Microsoft Windows — rc.exe.  Задача **RC** компилирует ресурсы, такие как курсоры, значки, растровые изображения, диалоговые окна и шрифты, в файл ресурсов \(RES\).  Дополнительные сведения см. в разделе "Компилятор ресурсов" на веб\-сайте [MSDN](http://go.microsoft.com/fwlink/?LinkId=737).  
  
## Параметры  
 В следующей таблице описаны параметры задачи RC.  Большинство параметров задач \(а также несколько наборов параметров\) соответствуют какому\-либо параметру командной строки.  
  
|Параметр|Описание|  
|--------------|--------------|  
|**AdditionalIncludeDirectories**|Необязательный параметр типа **String\[\]**.<br /><br /> Добавляет каталог к списку каталогов, в которых выполняется поиск включаемых файлов.<br /><br /> Дополнительные сведения см. в описании параметра **\/I** в разделе [Использование компилятора ресурсов \(командной строки RC\)](http://go.microsoft.com/fwlink/?LinkId=155730) на веб\-сайте MSDN.|  
|**AdditionalOptions**|Необязательный параметр типа **String**.<br /><br /> Список или пример параметров командной строки, **"***\/параметр1 \/параметр2 \/параметр\#*".  Этот параметр используется для задания параметров командной строки, не представленных другими параметрами задачи **RC**.<br /><br /> Дополнительные сведения см. в описании параметров в разделе [Использование компилятора ресурсов \(командной строки RC\)](http://go.microsoft.com/fwlink/?LinkId=155730) на веб\-сайте MSDN.|  
|**Culture**|Необязательный параметр типа **String**.<br /><br /> Указывает код языка, который представляет язык и региональные параметры, используемые в ресурсах.<br /><br /> Дополнительные сведения см. в описании параметра **\/l** в разделе [Использование компилятора ресурсов \(командной строки RC\)](http://go.microsoft.com/fwlink/?LinkId=155730) на веб\-сайте MSDN.|  
|**IgnoreStandardIncludePath**|Необязательный параметр типа **Boolean**.<br /><br /> Если он имеет значение `true`, то запрещается проверка компилятором ресурсов переменной среды INCLUDE при поиске файлов заголовков или файлов ресурсов.<br /><br /> Дополнительные сведения см. в описании параметра **\/x** в разделе [Использование компилятора ресурсов \(командной строки RC\)](http://go.microsoft.com/fwlink/?LinkId=155730) на веб\-сайте MSDN.|  
|**NullTerminateStrings**|Необязательный параметр типа **Boolean**.<br /><br /> Если он имеет значение `true`, то все строки в таблице строк заканчиваются значением NULL.<br /><br /> Дополнительные сведения см. в описании параметра **\/n** в разделе [Использование компилятора ресурсов \(командной строки RC\)](http://go.microsoft.com/fwlink/?LinkId=155730) на веб\-сайте MSDN.|  
|**PreprocessorDefinitions**|Необязательный параметр типа **String\[\]**.<br /><br /> Определите один или несколько символов препроцессора для компилятора ресурсов.  Укажите список символов макроса.<br /><br /> Дополнительные сведения см. в описании параметра **\/d** в разделе [Использование компилятора ресурсов \(командной строки RC\)](http://go.microsoft.com/fwlink/?LinkId=155730) на веб\-сайте MSDN.  Также см. **UndefinePreprocessorDefinitions** в этой таблице.|  
|**ResourceOutputFileName**|Необязательный параметр типа **String**.<br /><br /> Задает имя файла ресурса.  Укажите имя файла ресурсов.<br /><br /> Дополнительные сведения см. в описании параметра **\/fo** в разделе [Использование компилятора ресурсов \(командной строки RC\)](http://go.microsoft.com/fwlink/?LinkId=155730) на веб\-сайте MSDN.|  
|**ShowProgress**|Необязательный параметр типа **Boolean**.<br /><br /> Если он имеет значение `true`, то отображаются сообщения с отчетом о работе компилятора.<br /><br /> Дополнительные сведения см. в описании параметра **\/v** в разделе [Использование компилятора ресурсов \(командной строки RC\)](http://go.microsoft.com/fwlink/?LinkId=155730) на веб\-сайте MSDN.|  
|**Source**|Обязательный параметр типа `ITaskItem[]`.<br /><br /> Определяет массив элементов исходных файлов MSBuild, который может использоваться и создаваться задачами.|  
|**SuppressStartupBanner**|Необязательный параметр типа **Boolean**.<br /><br /> Если значение равно `true`, при запуске задачи не отображается сообщение об авторских правах и номере версии.<br /><br /> Для получения дополнительных сведений введите параметр командной строки **\/?**, а затем просмотрите описание параметра **\/nologo**.|  
|**TrackerLogDirectory**|Необязательный параметр типа **String**.<br /><br /> Задает каталог журнала отслеживания.|  
|**UndefinePreprocessorDefinitions**|Отменить символ препроцессора.<br /><br /> Дополнительные сведения см. в описании параметра **\/u** в разделе [Использование компилятора ресурсов \(командной строки RC\)](http://go.microsoft.com/fwlink/?LinkId=155730) на веб\-сайте MSDN.  Также см. **PreprocessorDefinitions** в этой таблице.|  
  
## Заметки  
  
## См. также  
 [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)