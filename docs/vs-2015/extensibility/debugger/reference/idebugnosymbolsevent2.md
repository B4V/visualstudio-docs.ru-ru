---
title: IDebugNoSymbolsEvent2 | Документация Майкрософт
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
- IDebugNoSymbolsEvent2 interface
ms.assetid: f6fb6388-47f6-4385-9ad5-95d62f9a7592
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fdb545bd55482d4c37cedd12fedc9e6cf52611e1
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49284015"
---
# <a name="idebugnosymbolsevent2"></a>IDebugNoSymbolsEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Сигналы [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] отладчика пользовательского интерфейса, чтобы предупредить пользователя, что символы не удалось найти для запущенный исполняемый файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
IDebugNoSymbolsEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Примечания для разработчиков  
 Реализуется отладчиков и потребляемых [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] отладчика пользовательского интерфейса.  
  
## <a name="requirements"></a>Требования  
 Заголовок: Msdbg.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

