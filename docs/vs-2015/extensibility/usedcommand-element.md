---
title: Элемент UsedCommand | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6956f4dd3d307808ff13aedc280a2af77fcc925d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49858983"
---
# <a name="usedcommand-element"></a>Элемент UsedCommand
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Позволяет VSPackage для доступа к команде, которая определена в другом vsct-файл. Например, если VSPackage использует стандарт **копирования** команду, которая определяется [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] оболочки, можно добавить команду в меню или панели инструментов без повторной реализации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|guid|Обязательно. Идентификатор GUID пары идентификатор GUID, который определяет команду.|  
|id|Обязательно. Идентификатор пары идентификатор GUID, который определяет команду.|  
|Условие|Необязательный. См. в разделе [условные атрибуты](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|Нет||  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент UsedCommands](../extensibility/usedcommands-element.md)|Группирует элементы UsedCommand и другими признаками UsedCommands.|  
  
## <a name="remarks"></a>Примечания  
 Добавив команду, чтобы `<UsedCommands>` элемента, сообщает VSPackage [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] среды, что VSPackage требует команды. Следует добавить `<UsedCommand>` элемент для любой команды, пакет необходимо, не могут быть включены во все версии и конфигурации из Visual Studio. Например, если пакет вызывает команду, которая используется только в Visual C++, команда не будет доступна пользователям Visual Web Developer Если не включить `<UsedCommand>` элемента для команды.  
  
## <a name="example"></a>Пример  
  
```  
<UsedCommands>  
  <UsedCommand guid="guidVSStd97" id="cmdidCut"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidCopy"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidPaste"/>  
</UsedCommands>  
```  
  
## <a name="see-also"></a>См. также  
 [Элемент UsedCommands](../extensibility/usedcommands-element.md)   
 [Файлы таблицы команд Visual Studio (VSCT-файлы)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

