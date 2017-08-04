---
title: "T4 Include Directive | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8c3de9f3-755a-47c5-a30a-65717dcaaac2
caps.latest.revision: 6
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 6
---
# T4 Include Directive
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

В текстовый шаблон в [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] можно включить текст из другого файла, воспользовавшись директивой `<#@include#>`.  Директивы `include` можно разместить в любом месте текстового шаблона перед первым блоком функций класса `<#+ ... #>`.  Включенные файлы также могут содержать директивы `include` и другие директивы.  Это позволяет использовать один и тот же код шаблона и стандартный текст в нескольких шаблонах.  
  
## Использование директив Include  
  
```  
<#@ include file="filePath" [once="true"] #>  
```  
  
-   Путь `filePath` может быть абсолютным или относительным для текущего файла шаблона.  
  
     Кроме того, отдельные расширения [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] могут задавать собственные каталоги для поиска включенных файлов.  Например, при установке пакета Visualization and Modeling SDK \(DSL Tools\) в список включения добавляется следующая папка: `Program Files\Microsoft Visual Studio 10.0\Common7\IDE\Extensions\Microsoft\DSL SDK\DSL Designer\11.0\TextTemplates`.  
  
     Эти дополнительные папки включения могут зависеть от расширения включающего файла.  Например, папка включения DSL Tools доступна только для включающих файлов с расширением `.tt`.  
  
-   `filePath` может включать переменные среды, отделенные знаком "%".  Пример.  
  
    ```  
    <#@ include file="%HOMEPATH%\MyIncludeFile.t4" #>  
    ```  
  
-   В имени включенного файла не обязательно использовать расширение `".tt"`.  
  
     Для включенных файлов можно использовать другое расширение, например `".t4"`.  Это объясняется тем, что при добавлении файла `.tt` в проект [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] автоматически задает для свойства **Специальный инструмент** значение `TextTemplatingFileGenerator`.  Как правило, не нужно, чтобы включенные файлы преобразовывались по отдельности.  
  
     С другой стороны, нужно помнить, что в некоторых случаях расширение файла влияет на то, в каких дополнительных папках будет выполнен поиск файлов включения.  Это может оказаться важным при наличии включенного файла, содержащего другие файлы.  
  
-   Включенное содержимое обрабатывается почти так же, как если бы оно было часть включающего текстового шаблона.  Однако можно включить файл, содержащий блок функций класса `<#+...#>`, даже если за директивой `include` следуют обычный текст и стандартные управляющие блоки.  
  
-   Используйте `once="true"`, чтобы убедиться, что шаблон включен только один раз, даже если он вызывался из нескольких других файлов include.  
  
     Эта функция упрощает создание библиотеки повторно используемых фрагментов T4, которые можно свободно использовать, не беспокоясь, что они включены в какой\-либо другой фрагмент. Например, предположим, что есть библиотека очень мелких фрагментов, связанных с обработкой шаблона и созданием кода C\#. В свою очередь, эти фрагменты используются еще в нескольких специальных средствах, например для создания исключений, которые затем можно использовать из более специализированного шаблона для приложений.  Если нарисовать граф зависимостей, можно увидеть, что некоторые фрагменты кода были бы включены несколько раз.  Но параметр `once` предотвращает последующие включения.  
  
 **MyTextTemplate.tt:**  
  
```  
<#@ output extension=".txt" #>  
Output message 1 (from top template).  
<#@ include file="TextFile1.t4"#>  
Output message 5 (from top template).  
<#  
   GenerateMessage(6); // defined in TextFile1.t4  
   AnotherGenerateMessage(7); // defined in TextFile2.t4  
#>  
  
```  
  
 **TextFile1.t4:**  
  
```  
   Output Message 2 (from included file).  
<#@include file="TextFile2.t4" #>  
   Output Message 4 (from included file).  
<#+ // Start of class feature control block.  
void GenerateMessage(int n)  
{  
#>  
   Output Message <#= n #> (from GenerateMessage method).  
<#+  
}  
#>  
  
```  
  
 **TextFile2.t4:**  
  
```  
        Output Message 3 (from included file 2).  
<#+ // Start of class feature control block.  
void AnotherGenerateMessage(int n)  
{  
#>  
       Output Message <#= n #> (from AnotherGenerateMessage method).  
<#+  
}  
#>  
  
```  
  
 **Сгенерированный в результате файл, MyTextTemplate.txt:**  
  
```  
Output message 1 (from top template).  
   Output Message 2 (from included file).  
        Output Message 3 (from included file 2).  
  
   Output Message 4 (from included file).  
  
Output message 5 (from top template).  
   Output Message 6 (from GenerateMessage method).  
       Output Message 7 (from AnotherGenerateMessage method).  
  
```  
  
##  <a name="msbuild"></a> Использование свойств проекта в MSBuild и Visual Studio  
 Хотя в директиве include можно использовать макросы Visual Studio, такие как $\(SolutionDir\), они не работают в MSBuild.  Если требуется преобразовывать шаблоны на компьютере сборки, необходимо использовать свойства проекта.  
  
 Измените CSPROJ\- или VBPROJ\-файл для определения свойства проекта.  В этом примере определяется свойство с именем `myIncludeFolder`.  
  
```xml  
<!-- Define a project property, myIncludeFolder: -->  
<PropertyGroup>  
    <myIncludeFolder>$(MSBuildProjectDirectory)\..\libs</myIncludeFolder>  
</PropertyGroup>  
  
<!-- Tell the MSBuild T4 task to make the property available: -->  
<ItemGroup>  
    <T4ParameterValues Include="myIncludeFolder">  
      <Value>$(myIncludeFolder)</Value>  
    </T4ParameterValues>  
  </ItemGroup>  
  
```  
  
 Теперь можно использовать свойство проекта в текстовых шаблонах, которые будут правильно преобразовываться как в Visual Studio, так и в MSBuild:  
  
```  
<#@ include file="$(myIncludeFolder)\defs.tt" #>  
```