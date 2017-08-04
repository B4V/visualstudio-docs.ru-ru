---
title: "Задача AL (компоновщик сборок) |Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#AL
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- AL task [MSBuild]
- MSBuild, AL task
ms.assetid: 2ddefbf2-5662-4d55-99a6-ac383bf44560
caps.latest.revision: 22
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: 3184299feb0834dc7e3b6980f4f3fed87b99092c
ms.contentlocale: ru-ru
ms.lasthandoff: 05/13/2017

---
# <a name="al-assembly-linker-task"></a>Задача AL (компоновщик сборок)
Задача AL включает AL.exe — инструмент, распространяемый с [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Этот компоновщик сборок используется для создания сборки с манифестом из одного или нескольких файлов, являющихся модулями или файлами ресурсов. Компиляторы и среды разработки обеспечивают указанные возможности, в связи с чем необходимость в непосредственном использовании этого задания возникает достаточно редко. Компоновщик сборок особенно полезен, если нужно создать единую сборку из нескольких файлов компонентов, например при разработке на нескольких языках. Эта задача не объединяет модули в один файл сборки. Отдельные модули должны оставаться распределенными и доступными для правильной загрузки результирующей сборки. Дополнительные сведения об инструменте AL.exe см. в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).  
  
## <a name="parameters"></a>Параметры  
 В следующей таблице приводятся параметры задачи `AL`.  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`AlgorithmID`|Необязательный параметр `String` .<br /><br /> Задает алгоритм хэширования всех файлов многофайловой сборки, кроме файла, содержащего манифест сборки. Дополнительные сведения см. в документации по параметру `/algid` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`BaseAddress`|Необязательный параметр `String` .<br /><br /> Задает адрес для загрузки библиотеки DLL на компьютер пользователя во время выполнения. Приложения загружаются быстрее, если задан базовый адрес DLL и операционная система не перемещает библиотеки в пространстве процесса. Этот параметр соответствует параметру /base[адрес] в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`CompanyName`|Необязательный параметр `String` .<br /><br /> Задает строковое значение поля `Company` в сборке. Дополнительные сведения см. в документации по параметру `/comp[any]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`Configuration`|Необязательный параметр `String` .<br /><br /> Задает строковое значение поля `Configuration` в сборке. Дополнительные сведения см. в документации по параметру `/config[uration]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`Copyright`|Необязательный параметр `String` .<br /><br /> Задает строковое значение поля `Copyright` в сборке. Дополнительные сведения см. в документации по параметру `/copy[right]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`Culture`|Необязательный параметр `String` .<br /><br /> Задает строковое значение языка и региональных параметров для связывания со сборкой. Дополнительные сведения см. в документации по параметру `/c[ulture]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`DelaySign`|Необязательный параметр `Boolean` .<br /><br /> Задайте значение `true`, чтобы разместить в сборке только открытый ключ, или `false`, чтобы полностью подписать сборку. Дополнительные сведения см. в документации по параметру `/delay[sign]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`Description`|Необязательный параметр `String` .<br /><br /> Задает строковое значение поля `Description` в сборке. Дополнительные сведения см. в документации по параметру `/descr[iption]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`EmbedResources`|Необязательный параметр <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Внедряет указанные ресурсы в образ, содержащий манифест сборки. Эта задача копирует содержимое файла ресурсов в образ. Элементы, передаваемые в этот параметр, могут иметь вложенные необязательные метаданные `LogicalName` и `Access`. Метаданные `LogicalName` используются для указания внутреннего идентификатора ресурса.  Для метаданных `Access` можно задать значение `private`, чтобы сделать данный ресурс невидимым для других сборок. Дополнительные сведения см. в документации по параметру `/embed[resource]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`EvidenceFile`|Необязательный параметр `String` .<br /><br /> Внедряет указанный файл в сборку с именем ресурса `Security.Evidence`.<br /><br /> Использовать имя `Security.Evidence` для обычных ресурсов нельзя. Этот параметр соответствует параметру `/e[vidence]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`ExitCode`|Необязательный выходной параметр `Int32`, доступный только для чтения.<br /><br /> Определяет код выхода, возвращаемый выполняемой командой.|  
|`FileVersion`|Необязательный параметр `String` .<br /><br /> Задает строковое значение поля `File Version` в сборке. Дополнительные сведения см. в документации по параметру `/fileversion` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`Flags`|Необязательный параметр `String` .<br /><br /> Задает значение для поля `Flags` в сборке. Дополнительные сведения см. в документации по параметру `/flags` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`GenerateFullPaths`|Необязательный параметр `Boolean` .<br /><br /> Указывает, что в задаче должны использоваться абсолютные пути для всех файлов, имена которых присутствуют в сообщении об ошибке. Этот параметр соответствует параметру `/fullpaths` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`KeyContainer`|Необязательный параметр `String` .<br /><br /> Задает контейнер, хранящий пару ключей. При этом сборка (ей следует присвоить строгое имя) будет подписана путем вставки открытого ключа в манифест сборки. Затем задача подпишет окончательную сборку с помощью закрытого ключа. Дополнительные сведения см. в документации по параметру `/keyn[ame]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`KeyFile`|Необязательный параметр `String` .<br /><br /> Задает файл, содержащий пару ключей или только открытый ключ для подписывания сборки. Компилятор вставляет открытый ключ в манифест сборки, а затем подписывает окончательную сборку закрытым ключом. Дополнительные сведения см. в документации по параметру `/keyf[ile]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`LinkResources`|Необязательный параметр <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Связывает указанные файлы ресурсов со сборкой. Ресурс становится частью сборки, но файл не копируется. Элементы, передаваемые в этот параметр, могут иметь вложенные необязательные метаданные `LogicalName`, `Target` и `Access`. Метаданные `LogicalName` используются для указания внутреннего идентификатора ресурса. Метаданные `Target` указывают путь и имя файла, в который задача копирует файл, после чего этот новый файл компилируется в сборку. Для метаданных `Access` можно задать значение `private`, чтобы сделать данный ресурс невидимым для других сборок. Дополнительные сведения см. в документации по параметру `/link[resource]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`MainEntryPoint`|Необязательный параметр `String` .<br /><br /> Задает полное имя (*класс.метод*) метода, являющегося точкой входа при преобразовании модуля в исполняемый файл. Этот параметр соответствует параметру `/main` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`OutputAssembly`|Необязательный выходной параметр <xref:Microsoft.Build.Framework.ITaskItem>.<br /><br /> Указывает имя файла, создаваемого этой задачей. Этот параметр соответствует параметру `/out` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`Platform`|Необязательный параметр `String` .<br /><br /> Ограничивает возможности выполнения кода одной из следующих платформ: `x86`, `Itanium`, `x64` или `anycpu`. Значение по умолчанию — `anycpu`. Этот параметр соответствует параметру `/platform` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`ProductName`|Необязательный параметр `String` .<br /><br /> Задает строковое значение поля `Product` в сборке. Дополнительные сведения см. в документации по параметру `/prod[uct]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`ProductVersion`|Необязательный параметр `String` .<br /><br /> Задает строковое значение поля `ProductVersion` в сборке. Дополнительные сведения см. в документации по параметру `/productv[ersion]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`ResponseFiles`|Необязательный параметр `String[]` .<br /><br /> Указывает файлы ответов, содержащие дополнительные параметры для прохождения к компоновщику сборок.|  
|`SdkToolsPath`|Необязательный параметр `String` .<br /><br /> Указывает путь к средствам пакета SDK, например resgen.exe.|  
|`SourceModules`|Необязательный параметр <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Один или несколько модулей для компиляции в сборку. Модули будут перечислены в манифесте результирующей сборки. Они должны будут оставаться распределенными и доступными для загрузки сборки. Элементы, передаваемые в этот параметр, могут иметь вложенные необязательные метаданные `Target`, указывающие путь и имя файла, в который задача копирует файл, после чего этот новый файл компилируется в сборку. Дополнительные сведения см. в документации по [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01). Этот параметр соответствует списку модулей, передаваемому в Al.exe без определенного параметра.|  
|`TargetType`|Необязательный параметр `String` .<br /><br /> Задает формат выходного файла: `library` (библиотека кода), `exe` (консольное приложение) или `win` (приложение Windows). Значение по умолчанию — `library`. Этот параметр соответствует параметру `/t[arget]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`TemplateFile`|Необязательный параметр `String` .<br /><br /> Указывает сборку, от которой требуется унаследовать все метаданные сборки, кроме поля языка и региональных параметров. Указанная сборка должна иметь строгое имя.<br /><br /> Сборка, созданная с использованием параметра `TemplateFile`, будет вспомогательной. Этот параметр соответствует параметру `/template` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`Timeout`|Необязательный параметр `Int32`.<br /><br /> Задает промежуток времени в миллисекундах, после которого исполняемый файл задачи прекращается. Значение по умолчанию — `Int.MaxValue`. Оно указывает, что период ожидания отсутствует.|  
|`Title`|Необязательный параметр `String` .<br /><br /> Задает строковое значение поля `Title` в сборке. Дополнительные сведения см. в документации по параметру `/title` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`ToolPath`|Необязательный параметр `String` .<br /><br /> Указывает расположение, из которого задача будет загружать базовый исполняемый файл (Al.exe). Если этот параметр не задан, задача использует путь установки пакета SDK, соответствующий версии платформы, на которой выполняется [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].|  
|`Trademark`|Необязательный параметр `String` .<br /><br /> Задает строковое значение поля `Trademark` в сборке. Дополнительные сведения см. в документации по параметру `/trade[mark]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`Version`|Необязательный параметр `String` .<br /><br /> Указывает сведения о версии для определенной сборки. Формат строки: *основной_номер_версии.дополнительный_номер_версии.сборка.редакция*. Значение по умолчанию — 0. Дополнительные сведения см. в документации по параметру `/v[ersion]` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`Win32Icon`|Необязательный параметр `String` .<br /><br /> Внедряет в сборку ICO-файл. ICO-файл является изображением значка выходного файла в проводнике. Этот параметр соответствует параметру `/win32icon` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
|`Win32Resource`|Необязательный параметр `String` .<br /><br /> Вставляет файл ресурсов Win32 (RES-файл) в выходной файл. Дополнительные сведения см. в документации по параметру `/win32res` в статье [Al.exe (компоновщик сборок)](http://msdn.microsoft.com/Library/b5382965-0053-47cf-b92f-862860275a01).|  
  
## <a name="remarks"></a>Примечания  
 Помимо перечисленных выше параметров, эта задача наследует параметры от класса <xref:Microsoft.Build.Tasks.ToolTaskExtension>, который, в свою очередь, наследует от класса <xref:Microsoft.Build.Utilities.ToolTask>. Список этих дополнительных параметров и их описания см. в статье [Базовый класс ToolTaskExtension](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Пример  
 В следующем примере создается сборка с заданными параметрами.  
  
```xml  
<AL  
    EmbedResources="@(EmbeddedResource)"  
    Culture="%(EmbeddedResource.Culture)"  
    TemplateFile="@(IntermediateAssembly)"  
    KeyContainer="$(KeyContainerName)"  
    KeyFile="$(KeyOriginatorFile)"  
    DelaySign="$(DelaySign)"  
  
    OutputAssembly=  
       "%(EmbeddedResource.Culture)\$(TargetName).resources.dll">  
  
    <Output TaskParameter="OutputAssembly"  
        ItemName="SatelliteAssemblies"/>  
</AL>  
```  
  
## <a name="see-also"></a>См. также  
 [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)   
 [Задачи](../msbuild/msbuild-tasks.md)