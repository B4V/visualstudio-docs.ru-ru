---
title: "Элемент Target (MSBuild) | Документы Майкрософт"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Target
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Target element [MSBuild]
- <Target> element [MSBuild]
ms.assetid: 350f6fc2-86b3-45f2-a31e-ece0e6bd4dca
caps.latest.revision: 34
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 0e5a449ef396e7b9fd23a2c018bdc7f8791b7b38
ms.openlocfilehash: 217f42db123e95557c2425b5678fb1ac9473c162
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="target-element-msbuild"></a>Элемент Target (MSBuild)
Содержит набор задач для [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] для последовательного выполнения.  

 \<Проект>  
 \<Target>  

## <a name="syntax"></a>Синтаксис  

```  
<Target Name="Target Name"  
        Inputs="Inputs"  
        Outputs="Outputs"  
        Returns="Returns"  
        KeepDuplicateOutputs="true/false"  
        BeforeTargets="Targets"  
        AfterTargets="Targets"  
        DependsOnTargets="DependentTarget"  
        Condition="'String A' == 'String B'">  
        Label="Label">  
    <Task>... </Task>  
    <PropertyGroup>... </PropertyGroup>  
    <ItemGroup>... </ItemGroup>  
    <OnError... />  
</Target>  
```  

## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  

### <a name="attributes"></a>Атрибуты  

|Атрибут|Описание|  
|---------------|-----------------|  
|`Name`|Обязательный атрибут.<br /><br /> Имя целевого объекта.|  
|`Condition`|Необязательный атрибут.<br /><br /> Проверяемое условие. Если условие принимает значение `false`, целевой объект не будет выполнять тело целевого объекта или любые целевые объекты, заданные в атрибуте `DependsOnTargets`. Дополнительные сведения об условиях см. в разделе [Условия](../msbuild/msbuild-conditions.md).|  
|`Inputs`|Необязательный атрибут.<br /><br /> Файлы, образующие входные данные для этого целевого объекта. При указании нескольких файлов они разделяются точкой с запятой. Отметки времени файлов будут сравниваться с отметками времени файлов в `Outputs` для определения актуальности `Target`. Дополнительные сведения см. в разделах [Добавочные сборки](../msbuild/incremental-builds.md), [Практическое руководство. Инкрементная сборка](../msbuild/how-to-build-incrementally.md) и [Преобразования](../msbuild/msbuild-transforms.md).|  
|`Outputs`|Необязательный атрибут.<br /><br /> Файлы, образующие выходные данные для этого целевого объекта. При указании нескольких файлов они разделяются точкой с запятой. Отметки времени файлов будут сравниваться с отметками времени файлов в `Inputs` для определения актуальности `Target`. Дополнительные сведения см. в разделах [Добавочные сборки](../msbuild/incremental-builds.md), [Практическое руководство. Инкрементная сборка](../msbuild/how-to-build-incrementally.md) и [Преобразования](../msbuild/msbuild-transforms.md).|  
|`Returns`|Необязательный атрибут.<br /><br /> Набор элементов, которые будут доступны для задач, вызывающих этот целевой объект, например задач MSBuild. Несколько целевых объектов разделяются точкой с запятой. Если целевые объекты в файле не имеют атрибутов `Returns`, для этой цели используются атрибуты Outputs.|  
|`KeepDuplicateOutputs`|Дополнительный логический атрибут.<br /><br /> Если указано значение `true`, в атрибут Returns целевого объекта записывается несколько ссылок на один и тот же элемент.  По умолчанию для атрибута устанавливается значение `false`.|  
|`BeforeTargets`|Необязательный атрибут.<br /><br /> Список имен целевых объектов, разделенных точкой с запятой.  Если указан, означает, что этот целевой объект должен выполняться перед указанным целевым объектом или объектами. Это позволяет автору проекта расширять существующий набор целевых объектов, не изменяя их напрямую. Дополнительные сведения см. в разделе [Порядок сборки целевых объектов](../msbuild/target-build-order.md).|  
|`AfterTargets`|Необязательный атрибут.<br /><br /> Список имен целевых объектов, разделенных точкой с запятой. Если указан, означает, что этот целевой объект должен выполняться после указанного целевого объекта или объектов. Это позволяет автору проекта расширять существующий набор целевых объектов, не изменяя их напрямую. Дополнительные сведения см. в разделе [Порядок сборки целевых объектов](../msbuild/target-build-order.md).|  
|`DependsOnTargets`|Необязательный атрибут.<br /><br /> Целевые объекты, которые должны быть выполнены, прежде чем можно будет выполнить этот целевой объект или анализ зависимостей верхнего уровня. Несколько целевых объектов разделяются точкой с запятой.|  
|`Label`|Необязательный атрибут.<br /><br /> Идентификатор, который используется для определения или упорядочения системных и пользовательских элементов.|  

### <a name="child-elements"></a>Дочерние элементы  

|Элемент|Описание|  
|-------------|-----------------|  
|[Задача](../msbuild/task-element-msbuild.md)|Создает и выполняет экземпляр задачи [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Целевой объект может содержать нуль и более задач.|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|Содержит набор определяемых пользователем элементов `Property`. Начиная с .NET Framework 3.5 элемент `Target` может содержать элементы `PropertyGroup`.|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|Содержит набор определяемых пользователем элементов `Item`. Начиная с .NET Framework 3.5 элемент `Target` может содержать элементы `ItemGroup`. Дополнительные сведения см. в разделе [Элементы](../msbuild/msbuild-items.md).|  
|[OnError](../msbuild/onerror-element-msbuild.md)|Вызывает один или несколько целевых объектов для выполнения, если атрибут `ContinueOnError` — ErrorAndStop (или `false`) для задачи, завершившейся ошибкой. Целевой объект может содержать нуль и более элементов `OnError`. Если элементы `OnError` присутствуют, они должны быть последними элементами в элементе `Target`.<br /><br /> Дополнительные сведения об атрибуте `ContinueOnError` см. в разделе [Элемент Task (MSBuild)](../msbuild/task-element-msbuild.md).|  

### <a name="parent-elements"></a>Родительские элементы  

|Элемент|Описание|  
|-------------|-----------------|  
|[Проект](../msbuild/project-element-msbuild.md)|Обязательный корневой элемент файла проекта [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].|  

## <a name="remarks"></a>Примечания  
 Первый целевой объект для выполнения задается во время выполнения. Целевые объекты могут иметь зависимости от других целевых объектов. Например, целевой объект для развертывания зависит от целевого объекта для компиляции. Обработчик [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] выполняет зависимости в том порядке, в котором они появляются в атрибуте `DependsOnTargets`, слева направо. Дополнительные сведения см. в разделе [Целевые объекты](../msbuild/msbuild-targets.md).  

 Целевой объект выполняется только один раз во время сборки, даже если от него зависит несколько целевых объектов.  

 Если целевой объект пропускается, из-за того что его атрибут `Condition` принимает значение `false`, его можно выполнить, если он вызывается позднее в сборке и в тот момент его атрибут `Condition` принимает значение `true`.  

 До выпуска MSBuild 4 атрибут `Target` возвращал все элементы, которые были заданы в атрибуте `Outputs`.  Для этого MSBuild приходилось записывать эти элементы в случае, если их запрашивали задачи, выполняющиеся позднее в сборке. Так как было невозможно указать, какие целевые объекты имели выходные данные, требуемые вызывающим объектам, MSBuild приходилось накапливать все элементы изо всех объектов `Outputs` для всех вызываемых объектов `Target`. Это приводило к проблемам масштабируемости для сборок, имеющих большое количество выходных элементов.  

 Если пользователь указывает `Returns` для любого элемента `Target` в проекте, то только те объекты `Target`, у которых имеется атрибут `Returns`, записывают эти элементы.  

 Объект `Target` может содержать оба атрибута: `Outputs` и `Returns`.  `Outputs` используется с `Inputs` для определения актуальности целевого объекта. `Returns`, если присутствует, переопределяет значение `Outputs`, чтобы определить, какие элементы возвращаются вызывающим объектам.  Если `Returns` не существует, то объекты `Outputs` будут доступны для вызывающих объектов, за исключением случая, описанного ранее.  

 До выпуска MSBuild 4, если `Target` включал несколько ссылок на один и тот же элемент в его объектах `Outputs`, выполнялась запись этих повторяющихся элементов. В очень больших сборках с большим объемом выходных данных и большим числом взаимозависимостей проекта, это приводило к потреблению большого объема памяти из-за записи ненужных повторяющихся элементов. Если для атрибута `KeepDuplicateOutputs` задано значение `true`, дубликаты записываются.  

## <a name="example"></a>Пример  
 В следующем примере кода показан элемент `Target`, выполняющий задачу `Csc`.  

```xml  
<Target Name="Compile" DependsOnTargets="Resources" Returns="$(TargetPath)">  
    <Csc Sources="@(CSFile)"  
          TargetType="library"  
          Resources="@(CompiledResources)"  
          EmitDebugInformation="$(includeDebugInformation)"  
          References="@(Reference)"  
          DebugType="$(debuggingType)" >  
        <Output TaskParameter="OutputAssembly"  
                  ItemName="FinalAssemblyName" />  
    </Csc>  
</Target>  
```  

## <a name="see-also"></a>См. также  
 [Целевые объекты](../msbuild/msbuild-targets.md)   
 [Справочник по схеме файла проекта](../msbuild/msbuild-project-file-schema-reference.md)
