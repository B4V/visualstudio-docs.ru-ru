---
title: IDebugThread2::GetThreadProperties | Документация Майкрософт
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
- IDebugThread2::GetThreadProperties
helpviewer_keywords:
- IDebugThread2::GetThreadProperties
ms.assetid: 304403fd-f4f8-4096-ac2c-bd3b59663aad
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ff8e2897ba3be9dc0703990582809dc508707912
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49810896"
---
# <a name="idebugthread2getthreadproperties"></a>IDebugThread2::GetThreadProperties
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Получает свойства, описывающие этот поток.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp#  
HRESULT GetThreadProperties (   
   THREADPROPERTY_FIELDS dwFields,  
   THREADPROPERTIES*     ptp  
);  
```  
  
```csharp  
int GetThreadProperties (   
   enum_THREADPROPERTY_FIELDS dwFields,  
   THREADPROPERTIES[]         ptp  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwFields`  
 [in] Сочетание флагов из [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md) перечисления, определяющее, какие поля `ptp` должны быть заполнены.  
  
 `ptp`  
 [in, out] Объект [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) структуры, который заполняется свойства потока.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Сведения, возвращаемые из этого метода обычно отображается в **потоков** окно отладки.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как реализовать этот метод для простого `CProgram` объект, реализующий [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) интерфейс.  
  
```cpp#  
HRESULT CProgram::GetThreadProperties(THREADPROPERTY_FIELDS dwFields,  
                                      THREADPROPERTIES *ptp)  
{  
    HRESULT hr = E_FAIL;    
  
    // Check for valid argument.    
   if (ptp)    
    {    
      // Create an array of buffers at ptp the size of the  
      // THREADPROPERTIES structure and set all of the  
      // buffers at ptp to 0.    
      memset(ptp, 0, sizeof (THREADPROPERTIES));    
  
      // Check if there is a valid THREADPROPERTY_FIELDS and the TPF_ID flag is set.    
      if (dwFields & TPF_ID)    
      {    
         // Check for successful assignment of the current thread ID to  
         //  the dwThreadId of the passed THREADPROPERTIES.    
         if (GetThreadId(&(ptp->dwThreadId)) == S_OK)    
         {    
            // Set the TPF_ID flag in the THREADPROPERTY_FIELDS enumerator    
            // of the passed THREADPROPERTIES.    
            ptp->dwFields |= TPF_ID;    
         }    
      }    
  
      hr = S_OK;    
    }    
    else    
        hr = E_INVALIDARG;    
  
    return hr;    
}    
```  
  
## <a name="see-also"></a>См. также  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)

