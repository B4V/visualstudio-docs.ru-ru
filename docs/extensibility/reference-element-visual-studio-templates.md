---
title: Ссылаться на элемент (шаблоны Visual Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Reference
helpviewer_keywords:
- Reference element [Visual Studio templates]
- <Reference> element [Visual Studio templates]
ms.assetid: 852772ea-c324-42e9-8c8a-6d565414a109
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b1f05bc8a19377576788fdb72400bf0af566b796
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39638115"
---
# <a name="reference-element-visual-studio-templates"></a>Элемент Reference (шаблоны Visual Studio)
Указывает ссылку на сборку, которую нужно добавить при добавлении элемента в проект.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Ссылки >  
 \<Ссылка >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Reference>  
    <Assembly> ... </Assembly>  
</Reference>  
```  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[Assembly](../extensibility/assembly-element-visual-studio-templates.md)|Обязательный элемент.<br /><br /> Указывает сведения о сборке, в шаблоне используется для добавления в проекты ссылки сборки. Должен содержать один `Assembly` элемента в каждом `Reference` элемент.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[Ссылки](../extensibility/references-element-visual-studio-templates.md)|Группы, которые добавляются в проекты ссылки на сборки.|  
  
## <a name="remarks"></a>Примечания  
 `Reference` — обязательный дочерний элемент элемента `References`.  
  
 `Reference` И `References` элементы могут использоваться только в *.vstemplate* файлы, имеющие `Type` значение атрибута `Item`.  
  
## <a name="example"></a>Пример  
 В следующем примере показано `TemplateContent` элемент шаблона элемента. Этот XML-код добавляет ссылки на *System.dll* и *System.Data.dll* сборок.  
  
```xml  
<TemplateContent>  
    <References>  
        <Reference>  
            <Assembly>  
                System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
        <Reference>  
            <Assembly>  
                System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
    </References>  
    ...  
</TemplateContent>  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по схеме для Visual Studio шаблон](../extensibility/visual-studio-template-schema-reference.md)   
 [Создание шаблонов проектов и элементов](../ide/creating-project-and-item-templates.md)
