---
title: IEnumDebugProcesses2::Next | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEnumDebugProcesses2::Next
helpviewer_keywords:
- IEnumDebugProcesses2::Next
ms.assetid: abef89eb-198b-49cd-a4c9-17bce6cac0e1
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f668f5c545404fdc7154f52c5d7e8d5695f6601e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49838417"
---
# <a name="ienumdebugprocesses2next"></a>IEnumDebugProcesses2::Next
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Возвращает следующий набор элементов из перечисления.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp#  
HRESULT Next(  
   ULONG            celt,  
   IDebugProcess2** rgelt,  
   ULONG*           pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint             celt,  
   IDebugProcess2[] rgelt,  
   ref uint         pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `celt`  
 [in] Количество извлекаемых элементов. Также указывает максимальный размер `rgelt` массива.  
  
 `rgelt`  
 [in, out] Массив [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) элементов для заполнения.  
  
 `pceltFetched`  
 [out] Возвращает количество элементов, фактически возвращенных в `rgelt`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`. Возвращает `S_FALSE` меньше, чем запрошенное количество элементов может быть возвращено; в противном случае возвращает код ошибки.  
  
## <a name="see-also"></a>См. также  
 [IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

