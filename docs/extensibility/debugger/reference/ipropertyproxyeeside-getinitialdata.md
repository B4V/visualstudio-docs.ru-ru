---
title: IPropertyProxyEESide::GetInitialData | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IPropertyProxyEESide::GetInitialData
helpviewer_keywords:
- IPropertyProxyEESide::GetInitialData
ms.assetid: 36cceb19-2604-4ef9-b42b-5dd30cbe24b1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 48f0a2fb9859b14a9fbbebd291604189da952b43
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49829655"
---
# <a name="ipropertyproxyeesidegetinitialdata"></a>IPropertyProxyEESide::GetInitialData
Возвращает начальные данные для этого объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetInitialData(  
   IEEDataStorage** dataOut  
);  
```  
  
```csharp  
int GetInitialData(  
   out IEEDataStorage dataOut  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dataOut`  
 [out] Возвращает [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) объект, содержащий начальные данные этого объекта.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## <a name="see-also"></a>См. также  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)