---
title: Элемент ProjectOutputFile | Документация Майкрософт
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectOutputFile element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 99f8173da22f631a1be74c18d4312f74958259e9
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37119457"
---
# <a name="projectoutputfile-element"></a>ProjectOutputFile - элемент
  Представляет выходные данные отдельного проекта для включения с элементом проекта при его развертывании в SharePoint.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<ProjectOutputFile ProjectId = "GUID of the project"  
    ProjectPath = "Relative path of the project"  
    Target = "Deployment path of the project output"  
    Type = "Type of deployment for the project output" />  
```  
  
## <a name="type"></a>Тип  
 **ProjectOutputFileType**  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|**ProjectId**|Требуется **xs: String** атрибута.<br /><br /> Идентификатор GUID зависимого проекта, который содержит выходные данные, которые вы хотите включить. Это соответствует **ProjectGuid** в файле зависимый проект.|  
|**ProjectPath**|Требуется **xs: String** атрибута.<br /><br /> Относительный путь, включая имя файла проекта зависимого проекта, который содержит выходные данные, которые вы хотите включить. Этот путь задается относительно корневой папки проекта SharePoint, который содержит элемент проекта SharePoint.|  
|**Целевой объект**|Необязательный **xs: String** атрибута.<br /><br /> Путь выходных файлов зависимого проекта для развертывания на сервере SharePoint, относительно корневой папки развертывания. Корневой папки развертывания определяется типом развертывания, заданные **тип** атрибута.<br /><br /> Дополнительные сведения см. в разделе описания **путь развертывания** и **Deployment Root** свойства SharePoint элементами проекта в среде [решения разработки SharePoint](../sharepoint/developing-sharepoint-solutions.md).|  
|**Type**|Требуется **xs: String** атрибута.<br /><br /> Тип развертывания для выходных данных зависимого проекта. Дополнительные сведения о возможных значениях см. в описании для **тип развертывания** свойства элементов проекта SharePoint в [решения разработки SharePoint](../sharepoint/developing-sharepoint-solutions.md).|  
  
### <a name="child-elements"></a>Дочерние элементы
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[Файлы](../sharepoint/files-element.md)|Указывает файлы, включаемые с элементом проекта SharePoint при развертывании в SharePoint.|  
  
## <a name="remarks"></a>Примечания  
 Используйте **ProjectOutputFile** элемент для включения вывода проекта в развертывании элемента проекта SharePoint. Можно указать другой проект, или же проект, который содержит элемент проекта. Дополнительные сведения см. в разделе [сведениями упаковки и развертывания в элементах проекта](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Сведения об элементе
  
|||  
|-|-|  
|**Пространство имен**|HTTP<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|  
|**Имя схемы**|Схема элемента проекта SharePoint|  
|**Файл проверки**|ProjectItemModelSchema.xsd|  
|**Может быть пустым**|Нет|  
  
## <a name="see-also"></a>См. также
 [Справочник по схеме для элемента проекта SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Предоставляют сведения о упаковки и развертывания в элементах проекта](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [Разработка решений SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
