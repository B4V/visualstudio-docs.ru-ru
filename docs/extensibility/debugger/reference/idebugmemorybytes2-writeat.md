---
title: IDebugMemoryBytes2::WriteAt | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMemoryBytes2::WriteAt
helpviewer_keywords:
- IDebugMemoryBytes2::WriteAt method
- WriteAt method
ms.assetid: 61cc3704-47fa-4d9b-aa62-bb4585ac8fb1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a2d164f0ef816285e2df4a9e49b09d55feb90d25
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49864275"
---
# <a name="idebugmemorybytes2writeat"></a>IDebugMemoryBytes2::WriteAt
Записывает указанное число байтов памяти, начиная с указанного адреса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT WriteAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory  
);  
```  
  
```csharp  
int WriteAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pStartContext`  
 [in] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) объект, который указывает, где начинается запись байтов.  
  
 `dwCount`  
 [in] Число байтов для записи.  
  
 `rgbMemory`  
 [in] Запись байтов. Этот массив предполагается, что по крайней мере `dwCount` байт размером.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает `S_FALSE` Если не все байты, может быть записан или возвращает код ошибки (обычно `E_FAIL`).  
  
## <a name="remarks"></a>Примечания  
 Если начальный адрес находится за пределами окна "память", представленный данным [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) объекта, запись не выполняется и кодом ошибки `E_FAIL` возвращается, даже если перекрывается сумму для записи в области памяти.  
  
## <a name="see-also"></a>См. также  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)