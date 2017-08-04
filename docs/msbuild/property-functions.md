---
title: "Функции свойств | Документы Майкрософт"
ms.custom: 
ms.date: 02/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, property functions
ms.assetid: 2253956e-3ae0-4bdc-9d3a-4881dfae4ddb
caps.latest.revision: 33
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
ms.sourcegitcommit: 203e1e27cc892e96b103fc6cb22a73672a8e16af
ms.openlocfilehash: f351952a256679ec2d6c9dc2daa5288ca7214ad0
ms.lasthandoff: 03/01/2017

---
# <a name="property-functions"></a>Функции свойств
В версиях 4 и 4.5 платформы .NET Framework можно оценивать скрипты MSBuild с помощью функции свойства. Функции свойства можно использовать во всех случаях, где появляются свойства. В отличие от задач, функции свойства можно использовать за пределами целей и оценивать до запуска целей.  

 Без использования задач MSBuild вы можете читать системное время, сравнивать строки, сопоставлять регулярные выражения и выполнять другие действия в скрипте построения. MSBuild попытается преобразовать строку в число и число в строку и при необходимости выполнит другие преобразования.  

## <a name="property-function-syntax"></a>Синтаксис функции свойства  
 Существуют три типа функций свойства, каждая из которых имеет свой синтаксис.  

-   Функции свойства строки (экземпляра)  

-   Функции статичного свойства  

-   Функции свойства MSBuild  

### <a name="string-property-functions"></a>Функции свойства строки  
 Все значения свойства построения являются значениями строки. Для управления значением свойства можно использовать методы строки (экземпляра). Например, можно извлечь имя диска (первые три символа) из свойства построения, которое представляет собой полный путь, с помощью следующего кода.  

 `$(ProjectOutputFolder.Substring(0,3))`  

### <a name="static-property-functions"></a>Функции статичного свойства  
 В скрипте построения можно получить доступ к статическим свойствам и методам многих системных классов. Чтобы получить значение статического свойства, используйте следующий синтаксис, где *Class* — это имя системного класса, а *Property* — это имя свойства.  

 `$([Class]::Property)`  

 Например, чтобы задать свойство построения на текущую дату и время, можно использовать следующий код.  

 `<Today>$([System.DateTime]::Now)</Today>`  

 Чтобы вызвать статический метод, используйте следующий синтаксис, где *Class* — это имя системного класса, *Method* — это имя метода, а *(Parameters)* — это список параметров метода.  

 `$([Class]::Method(Parameters))`  

 Например, чтобы задать свойство построения на новый GUID, можно использовать следующий скрипт.  

 `<NewGuid>$([System.Guid]::NewGuid())</NewGuid>`  

 В функциях статического свойства можно использовать любой статический метод или свойство следующих системных классов.  

-   System.Byte  

-   System.Char  

-   System.Convert  

-   System.DateTime  

-   System.Decimal  

-   System.Double  

-   System.Enum  

-   System.Guid  

-   System.Int16  

-   System.Int32  

-   System.Int64  

-   System.IO.Path  

-   System.Math  

-   System.UInt16  

-   System.UInt32  

-   System.UInt64  

-   System.SByte  

-   System.Single  

-   System.String  

-   System.StringComparer  

-   System.TimeSpan  

-   System.Text.RegularExpressions.Regex  

-   Microsoft.Build.Utilities.ToolLocationHelper  

 Кроме этого, можно использовать следующие статические методы и свойства.  

-   System.Environment::CommandLine  

-   System.Environment::ExpandEnvironmentVariables  

-   System.Environment::GetEnvironmentVariable  

-   System.Environment::GetEnvironmentVariables  

-   System.Environment::GetFolderPath  

-   System.Environment::GetLogicalDrives  

-   System.IO.Directory::GetDirectories  

-   System.IO.Directory::GetFiles  

-   System.IO.Directory::GetLastAccessTime  

-   System.IO.Directory::GetLastWriteTime  

-   System.IO.Directory::GetParent  

-   System.IO.File::Exists  

-   System.IO.File::GetCreationTime  

-   System.IO.File::GetAttributes  

-   System.IO.File::GetLastAccessTime  

-   System.IO.File::GetLastWriteTime  

-   System.IO.File::ReadAllText  

### <a name="calling-instance-methods-on-static-properties"></a>Вызов методов экземпляра на статических свойствах  
 При доступе к статическому свойству, которое возвращает экземпляр объектов, можно вызывать методы экземпляра этого объекта. Чтобы вызвать метод экземпляра, используйте следующий синтаксис, где *Class* — это имя системного класса, *Property* — это имя свойства, *Method* — это имя метода, а *(Parameters)* — это список параметров метода.  

 `$([Class]::Property.Method(Parameters))`  

 Имя класса должно содержать полное пространство имен.  

 Например, чтобы задать свойство построения на текущую дату, можно использовать следующий код.  

 `<Today>$([System.DateTime]::Now.ToString("yyyy.MM.dd"))</Today>`  

### <a name="msbuild-property-functions"></a>Функции свойства MSBuild  
 Для обеспечения арифметической побитовой логической поддержки escape-символов можно использовать несколько статических методов из вашего построения. Получить доступ к этим методам можно с помощью следующего синтаксиса, где *Method* — это имя метода, а *Parameters* — это список параметров метода.  

 `$([MSBuild]::Method(Parameters))`  

 Например, чтобы добавить два свойства с числовыми значениями, используйте следующий код.  

 `$([MSBuild]::Add($(NumberOne), $(NumberTwo))`  

 Приведем список функций свойства MSBuild.  

|Подпись функции|Описание|  
|------------------------|-----------------|  
|Сложение double(double a, double b)|Сложение двух значений double.|  
|Сложение long(long a, long b)|Сложение двух значений long.|  
|Вычитание double(double a, double b)|Вычитание двух значений double.|  
|Вычитание long(long a, long b)|Вычитание двух значений long.|  
|Умножение double(double a, double b)|Умножение двух значений double.|  
|Умножение long(long a, long b)|Умножение двух значений long.|  
|Деление double(double a, double b)|Деление двух значений double.|  
|Деление long(long a, long b)|Деление двух значений long.|  
|Остаток от деления double (double a, double b)|Остаток от деления двух значений double.|  
|Остаток от деления long(long a, long b)|Остаток от деления двух значений long.|  
|строка Escape (строка не экранируется)|Escape-последовательность строки в соответствии с правилами экранирования MSBuild.|  
|строка Unescape (строка экранируется)|Unescape-последовательность строки в соответствии с правилами экранирования MSBuild.|  
|Целое значение BitwiseOr(первое целое значение, второе целое значение)|Примените побитовый параметр `OR` к первому и второму значению (первое &#124; второе).|  
|Целое значение BitwiseAnd(первое целое значение, второе целое значение)|Примените побитовый параметр `AND` к первому и второму значению (первое & второе).|  
|Целое значение BitwiseXor(первое целое значение, второе целое значение)|Примените побитовый параметр `XOR` к первому и второму значению (первое ^ второе).|  
|Целое значение BitwiseNot(первое целое значение)|Примените побитовый параметр `NOT` (~первое значение).|  

##  <a name="nested-property-functions"></a>Вложенные функции свойства  
 Функции свойства можно объединять для формирования более сложных функций, как показано в следующем примере.  

 `$([MSBuild]::BitwiseAnd(32, $([System.IO.File]::GetAttributes(tempFile))))`  

 В этом примере возвращается значение <xref:System.IO.FileAttributes>`Archive` бит (32 или 0) файла, указанного в пути `tempFile`. Обратите внимание, что значения перечисляемых данных не могут отображаться в функциях свойства по имени. Вместо этого необходимо использовать числовое значение (32).  

 Во вложенных функциях свойства могут также появляться метаданные. Дополнительные сведения см. в статье [Пакетная обработка](../msbuild/msbuild-batching.md).  

##  <a name="msbuild-doestaskhostexist"></a>MSBuild DoesTaskHostExist  
 Функция свойства `DoesTaskHostExist` в MSBuild возвращает сведения об установленном сервере задач для указанной среды выполнения и значение архитектуры.  

 Эта функция свойства использует следующий синтаксис.  

```  
$[MSBuild]::DoesTaskHostExist(string theRuntime, string theArchitecture)  
```  

##  <a name="msbuild-ensuretrailingslash"></a>MSBuild EnsureTrailingSlash  
 Функция свойства `EnsureTrailingSlash` в MSBuild добавляет косую черту, если таковая отсутствует.  

 Эта функция свойства использует следующий синтаксис.  

```  
$([MSBuild]::EnsureTrailingSlash('$(PathProperty)')  
```  

##  <a name="msbuild-getdirectorynameoffileabove"></a>MSBuild GetDirectoryNameOfFileAbove  
 Функция свойства `GetDirectoryNameOfFileAbove` в MSBuild выполняет поиск файла в каталогах выше текущего каталога в пути.  

 Эта функция свойства использует следующий синтаксис.  

```  
$[MSBuild]::GetDirectoryNameOfFileAbove(string ThePath, string TheFile)  
```  

 В следующем коде показан пример этого синтаксиса.  

```xml  
<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), EnlistmentInfo.props))\EnlistmentInfo.props" Condition=" '$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), EnlistmentInfo.props))' != '' " />  
```  

##  <a name="msbuild-getpathoffileabove"></a>MSBuild GetPathOfFileAbove  
 Функция свойства `GetPathOfFileAbove` в MSBuild возвращает путь к файлу, непосредственно предшествующему данному. Она функционально эквивалентна вызову.

 ```<Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), dir.props))\dir.props" />```

 Эта функция свойства использует следующий синтаксис.  

```  
$([MSBuild]::GetPathOfFileAbove(dir.props)  
```  

##  <a name="msbuild-getregistryvalue"></a>MSBuild GetRegistryValue  
 Функция свойства `GetRegistryValue` в MSBuild возвращает значение раздела реестра. Она принимает два аргумента — имя раздела и имя значения — и возвращает значение в реестр. Если не указано имя значения, возвращается значение по умолчанию.  

 В следующих примерах показано, как используется эта функция.  

```  
$([MSBuild]::GetRegistryValue(`HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\10.0\Debugger`, ``))                                  // default value  
$([MSBuild]::GetRegistryValue(`HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\10.0\Debugger`, `SymbolCacheDir`))  
$([MSBuild]::GetRegistryValue(`HKEY_LOCAL_MACHINE\SOFTWARE\(SampleName)`, `(SampleValue)`))             // parens in name and value  

```  

##  <a name="msbuild-getregistryvaluefromview"></a>MSBuild GetRegistryValueFromView  
 Функция свойства `GetRegistryValueFromView` в MSBuild получает данные системного реестра с учетом раздела реестра, значения и одного или нескольких упорядоченных представлений реестра. Раздел и значения ищутся в каждом представлении реестра по порядку, пока не будут найдены.  

 Синтаксис функции свойства.  

 [MSBuild\]::GetRegistryValueFromView(string keyName, string valueName, object defaultValue, params object[] views)  

 64-разрядная операционная система Windows ведет раздел реестра HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node, содержащий представление реестра HKEY_LOCAL_MACHINE\SOFTWARE для 32-разрядных приложений.  

 По умолчанию 32-разрядное приложение, работающее на WOW64, получает доступ к 32-разрядному представлению реестра, а 64-разрядное приложение — к 64-разрядному представлению реестра.  

 Доступны следующие представления реестра.  

|Представление реестра|Определение|  
|-------------------|----------------|  
|RegistryView.Registry32|Представление реестра для 32-разрядного приложения.|  
|RegistryView.Registry64|Представление реестра для 64-разрядного приложения.|  
|RegistryView.Default|Представление реестра, совпадающее с процессом, на котором работает приложение.|  

 Пример.  

 `$([MSBuild]::GetRegistryValueFromView('HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SDKs\Silverlight\v3.0\ReferenceAssemblies', 'SLRuntimeInstallPath', null, RegistryView.Registry64, RegistryView.Registry32))`  

 Получение данных SLRuntimeInstallPath из раздела ReferenceAssemblies, поиск сначала в 64-разрядном, а затем в 32-разрядном представлении реестра.  

##  <a name="msbuild-makerelative"></a>MSBuild MakeRelative  
 Функция свойства `MakeRelative` в MSBuild возвращает путь второго пути относительно первого пути. Каждый путь может быть файлом или папкой.  

 Эта функция свойства использует следующий синтаксис.  

```  
$[MSBuild]::MakeRelative($(FileOrFolderPath1), $(FileOrFolderPath2))  
```  

 В следующем коде показан пример этого синтаксиса.  

```xml  
<PropertyGroup>  
    <Path1>c:\users\</Path1>  
    <Path2>c:\users\username\</Path2>  
</PropertyGroup>  

<Target Name = "Go">  
    <Message Text ="$([MSBuild]::MakeRelative($(Path1), $(Path2)))" />  
    <Message Text ="$([MSBuild]::MakeRelative($(Path2), $(Path1)))" />  
</Target>  

<!--  
Output:  
   username\  
   ..\  
-->  
```  

##  <a name="msbuild-valueordefault"></a>MSBuild ValueOrDefault  
 Функция свойства `ValueOrDefault` в MSBuild возвращает первый аргумент, если он не нулевой или пустой. Если первый аргумент нулевой, функция возвращает второй аргумент.  

 В следующем примере показано, как используется эта функция.  

```xml  
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  

    <PropertyGroup>  
        <Value1>$([MSBuild]::ValueOrDefault(`$(UndefinedValue)`, `a`))</Value1>  
        <Value2>$([MSBuild]::ValueOrDefault(`b`, `$(Value1)`))</Value2>  
    </PropertyGroup>  

    <Target Name="MyTarget">  
        <Message Text="Value1 = $(Value1)" />  
        <Message Text="Value2 = $(Value2)" />  
    </Target>  
</Project>  

<!--  
Output:   
  Value1 = a  
  Value2 = b  
-->  
```

## <a name="see-also"></a>См. также
[MSBuild Properties](../msbuild/msbuild-properties.md)  (Свойства MSBuild)  
[MSBuild Overview](../msbuild/msbuild.md) (Общие сведения о MSBuild)
