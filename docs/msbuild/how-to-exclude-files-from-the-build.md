---
title: "Практическое руководство. Исключение файлов из сборки | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, wildcards
- MSBuild, excluding files
- wildcards, MSBuild
ms.assetid: 1be36e45-01da-451c-972d-f9fc0e7d663c
caps.latest.revision: 16
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
ms.sourcegitcommit: 3ba7680d46345f2b49019659c715cfb418933d39
ms.openlocfilehash: 09a5ecabf88a9f15bcd84bd83ffac5730680adae
ms.lasthandoff: 02/22/2017

---
# <a name="how-to-exclude-files-from-the-build"></a>Практическое руководство. Исключение файлов из построения
В файле проекта можно использовать подстановочные знаки, чтобы включить все файлы из одного каталога или набора вложенных каталогов в качестве входных данных для сборки. Однако может присутствовать один файл в каталоге или один каталог в наборе вложенных каталогов, который не требуется включать в качестве входных данных для сборки. Этот файл или каталог можно явным образом исключить из списка входных данных. Кроме того, в проекте может быть файл, который требуется включить только при определенных условиях. Можно явно объявить условия, при которых файл включается в сборку.  
  
## <a name="excluding-a-file-or-directory-from-the-inputs-for-a-build"></a>Исключение файла или каталога из входных данных для сборки  
 Списки элементов являются входными файлами для сборки. Элементы, которые требуется включить, объявляются отдельно или в составе группы с помощью атрибута `Include`. Например:  
  
```xml  
<CSFile Include="Form1.cs"/>  
<CSFile Include ="File1.cs;File2.cs"/>  
<CSFile Include="*.cs"/>  
<JPGFile Include="Images\**\*.jpg"/>  
```  
  
 Если вы использовали подстановочные знаки для включения всех файлов в одном каталоге или наборе вложенных каталогов в качестве входных данных для сборки, может присутствовать один или несколько файлов или каталог, которые не требуется включать. Чтобы исключить элемент из списка элементов, используйте атрибут `Exclude`.  
  
#### <a name="to-include-all-cs-or-vb-files-except-form2"></a>Включение всех файлов с расширением CS или VB, кроме Form2  
  
-   Используйте один из следующих атрибутов `Include` и `Exclude`:  
  
    ```xml  
    <CSFile Include="*.cs" Exclude="Form2.cs"/>  
    ```  
  
     - или  
  
    ```xml  
    <VBFile Include="*.vb" Exclude="Form2.vb"/>  
    ```  
  
#### <a name="to-include-all-cs-or-vb-files-except-form2-and-form3"></a>Включение всех файлов с расширением CS или VB, кроме Form2 и Form3  
  
-   Используйте один из следующих атрибутов `Include` и `Exclude`:  
  
    ```xml  
    <CSFile Include="*.cs" Exclude="Form2.cs;Form3.cs"/>  
    ```  
  
     - или  
  
    ```xml  
    <VBFile Include="*.vb" Exclude="Form2.vb;Form3.vb"/>  
    ```  
  
#### <a name="to-include-all-jpg-files-in-subdirectories-of-the-images-directory-except-those-in-the-version2-directory"></a>Включение всех JPG-файлов в подкаталогах каталога Images, кроме файлов из каталога Version2  
  
-   Используйте следующие атрибуты `Include` и `Exclude`:  
  
    ```xml  
    <JPGFile  
        Include="Images\**\*.jpg"  
        Exclude = "Images\**\Version2\*.jpg"/>  
    ```  
  
    > [!NOTE]
    >  Нужно указать путь для обоих атрибутов. Если вы используете абсолютный путь для указания расположения файлов в атрибуте `Include`, нужно использовать абсолютный путь и в атрибуте `Exclude`. Если же вы используете относительный путь в атрибуте `Include`, такой путь нужно использовать и в атрибуте `Exclude`.  
  
## <a name="using-conditions-to-exclude-a-file-or-directory-from-the-inputs-for-a-build"></a>Использование условий для исключения файла или каталога из входных данных для сборки  
 Если имеются элементы, которые требуется включить, например, в отладочную сборку, но не в сборку выпуска, можно использовать атрибут `Condition`, чтобы указать условия для включения элемента.  
  
#### <a name="to-include-the-file-formulavb-only-in-release-builds"></a>Включение файла Formula.vb только в сборки выпуска  
  
-   Используйте атрибута `Condition` по аналогии со следующей процедурой:  
  
    ```xml  
    <Compile  
        Include="Formula.vb"  
        Condition=" '$(Configuration)' == 'Release' " />  
    ```  
  
## <a name="example"></a>Пример  
 В следующем примере кода выполняется сборка проекта со всеми CS-файлами из каталога, кроме файла Form2.cs.  
  
```xml  
<Project DefaultTargets="Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <PropertyGroup>  
        <builtdir>built</builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <CSFile Include="*.cs Exclude="Form2.cs"/>  
  
        <Reference Include="System.dll"/>  
        <Reference Include="System.Data.dll"/>  
        <Reference Include="System.Drawing.dll"/>  
        <Reference Include="System.Windows.Forms.dll"/>  
        <Reference Include="System.XML.dll"/>  
    </ItemGroup>  
  
    <Target Name="PreBuild">  
        <Exec Command="if not exist $(builtdir) md $(builtdir)"/>  
    </Target>  
  
    <Target Name="Compile" DependsOnTargets="PreBuild">  
        <Csc Sources="@(CSFile)"  
            References="@(Reference)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).exe"  
            TargetType="exe" />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>См. также  
 [Элементы](../msbuild/msbuild-items.md)   
 [MSBuild](../msbuild/msbuild.md)
 [Практическое руководство. Выбор файлов для сборки](../msbuild/how-to-select-the-files-to-build.md)