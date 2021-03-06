---
title: Флаги командной строки компилятора VSCT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, compiling
- command-table file compilation (VSCT files)
ms.assetid: 9dc6c33f-e6cf-4cf2-9b05-e8f7bfac1cfb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6e2e1045adb451c7f4dd06b888fca356d26b7ff3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31139777"
---
# <a name="vsct-compiler-command-line-flags"></a>Флаги командной строки компилятора VSCT
Параметры командной строки для обеспечения успешной компиляции vsct-файлами в компиляторе Visual Studio команды таблицы (VSCT).  
  
## <a name="command-line-parameters"></a>Параметры командной строки  
 Для просмотра основную справку VSCT из [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **команда** окно, перейдите к *путь установки Visual Studio SDK*\VisualStudioIntegration\Tools\Bin\ папку и введите:  
  
```  
vsct /?  
```  
  
 Это возвращает:  
  
```  
Microsoft (R) Visual Studio (R) Command Table Compiler Version 3.00.2000  
  
Syntax: vsct <infile> [<outfile>] [-S[symbols file]] [-D<preprocessor-define>]*  
[-I<include-path>]* [-L<language>] [-E[C|H|N]:<name>]  
  
  -D    Specify any additional preprocessor defines  
  -I    Indcate what additional include paths to send to the preprocessor  
  -L    Specify the langauge to use when selecting strings  
  -E    Emit C# objects in the specified namespace for command items,  
        folowed by [L|F|H|N]:<value>  
        F = Name of the file to emit (used if -EL is provided)  
        L = Name of a language providing a CodeDOM provider  
        N = namespace (required if -EL is provided)  
        H = C++ header  
  -c    Clean build skipping dependancy checks  
  -v    Verbose output  
```  
  
> [!NOTE]
>  Символы - (дефис) и / (косая черта) являются оба принятые нотации, указывающий параметры командной строки.  
  
 Ниже приводятся Допустимые флаги и их значения.  
  
|Параметр|Описание|  
|------------|-----------------|  
|-D|Укажите любые дополнительные определенных символов.|  
|-I|Указать, что дополнительные включения путей, которые должны использоваться при разрешении ссылок на файлы.|  
|-L|Укажите <xref:System.Globalization.CultureInfo> имя языка и региональных параметров, например «en US».|  
|-E|Возвращает объектов C# в указанное пространство имен для элементов команды, за которым следует [C&#124;H&#124;N]:*filename*где C = C#, H = заголовок C++, N = пространство имен. Пространство имен является обязательным для C#.|  
|-v|Подробный вывод.|  
  
 Параметр -L указывает компилятору на необходимость выбрать группу строк для получения двоичного cto-файла, соответствующее заданной <xref:System.Globalization.CultureInfo> имя языка и региональных параметров. Имя указанного языка и региональных параметров должно соответствовать атрибут Language из одного или нескольких [элемент строки](../../extensibility/strings-element.md) в vsct-файле. Если строки у элемента есть нет атрибут Language, оно наследуется от содержащего [CommandTable элемент](../../extensibility/commandtable-element.md).  
  
 Vsct-файл может иметь несколько элементов строк, и каждый может быть другой атрибут языка. Глобализация достигается, запустив компилятора VSCT несколько раз и изменив параметр -L для каждого имени языка и региональных параметров.  
  
 Если имя языка и региональных параметров, заданное в параметре -L не соответствует атрибут Language любого элемента строки, компилятор будет пытаться соответствуют языка, а не как область. Например если не удается найти «en US», компилятор пытается вместо «en». После неудачной будет предпринята попытка текущего языка и региональных параметров операционной системы. После неудачной компиляции на первый элемент строки, найденные.  
  
 Параметр -E можно использовать для создания файла C-стиле заголовка, который содержит символы, используемые таблицы команд или для создания файла C#, содержащий объекты для управляющие символы.  
  
 -D и - I коммутаторы синтаксически флаги препроцессора Cl.exe C, которые имеют одинаковое имя. -D для возможности расширения на основе XML используются определения, которые имеют формат X = Y \<определенные > тесты в `Condition` атрибуты. -I включить пути используются для разрешения \<Include >, \<Extern > и \<точечный рисунок > ссылки на файлы. Дополнительные сведения см. в разделе [Справочник по схеме XML VSCT](../../extensibility/vsct-xml-schema-reference.md).  
  
 Компилятор VSCT можно также декомпилировать ранее собранную двоичный файл. Чтобы сделать это, укажите двоичный файл для \<входной_файл >.   Если двоичный файл был создан с помощью компилятора VSCT, он будет иметь уже внедренных символов и вывод с символические имена в \<символы > разделе выходных данных. Если двоичный файл был создан компилятором CTC, выход будет содержать фактические значения GUID и идентификаторы. В случае *.ctsym файла, формируемого с текущими версиями Ctc.exe в той же папке, как двоичный файл входные символы загружены из этого файла и используется для вывода.  
  
## <a name="see-also"></a>См. также  
 [Таблицы команд Visual Studio (. Файлы Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Справочник по схеме VSCT XML](../../extensibility/vsct-xml-schema-reference.md)   
 [Как добавить элементы пользовательского интерфейса с помощью пакетов VSPackage](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)