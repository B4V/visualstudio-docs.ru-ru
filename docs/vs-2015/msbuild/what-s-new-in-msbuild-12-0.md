---
title: Новые возможности MSBuild 12.0 | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9976a6ad-c052-4017-b848-35b5ae4a2f66
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f10fa5496795947c041482d5ae5dc7b6112da67
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49247407"
---
# <a name="what39s-new-in-msbuild-120"></a>Новые возможности MSBuild 12.0
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

MSBuild теперь устанавливается вместе с Visual Studio, а не в составе платформы .NET Framework. Номер текущей версии MSBuild — 12.0. Если вы хотите установить MSBuild отдельно, скачайте пакет установки на странице [скачиваемых материалов MSBuild](http://go.microsoft.com/fwlink/?LinkId=309745).  
  
## <a name="changed-path"></a>Измененный путь  
 Теперь MSBuild устанавливается непосредственно в каталог *%ProgramFiles%* — например, в C:\Program Files\MSBuild\\.  
  
## <a name="changed-properties"></a>Измененные свойства  
 В связи с выходом нового номера версии изменены следующие свойства MSBuild:  
  
-   `MSBuildToolsVersion` для этой версии средств — 12.0.  
  
-   Теперь `MSBuildToolsPath` — %ProgramFiles%\MSBuild\12.0\bin в 32-разрядных операционных системах или %ProgramFiles%\MSBuild\12.0\bin\amd64 в 64-разрядных операционных системах.  
  
-   Значения `ToolsVersion` можно найти в HKLM\SOFTWARE\Microsoft\MSBuild\ToolsVersions\12.0 в 32-разрядных операционных системах или в HKLM\SOFTWARE\Wow6432Node\Microsoft\MSBuild\ToolsVersions\12.0 в 64-разрядных операционных системах.  
  
-   Свойства `SDK35ToolsPath` и `SDK40ToolsPath` свойства указывают на пакет SDK для .NET Framework, поставляемый с данной версией Visual Studio (например, 8.1A для инструментов 4.X).  
  
## <a name="new-properties"></a>Новые свойства  
  
-   `MSBuildFrameworkToolsPath` является новым свойством со значением %windir%\Microsoft.NET\Framework\v4.0.30319 в 32-разрядных операционных системах или %windir%\Microsoft.NET\Framework64\v4.0.30319 в 64-разрядных операционных системах. Оно заменяет свойство `MSBuildToolsPath`, которое может использоваться для указания на инструменты и служебные программы .NET Framework.  
  
-   Свойства `MSBuildToolsPath` и `MSBuildFrameworkToolsPath` имеют 32-разрядные эквиваленты — `MSBuildToolsPath32` и `MSBuildFrameworkToolsPath32`, — которые всегда указывают на расположение 32-разрядной версии независимо от того, используется ли 32-разрядная или 64-разрядная версия MSBuild.

## <a name="see-also"></a>См. также
[MSBuild](msbuild.md)


