---
title: IDebugProgram2::Step | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::Step
helpviewer_keywords:
- IDebugProgram2::Step
ms.assetid: e4c2ffce-9810-4088-8162-eac9ef04f2a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 489a641e0f42f6e8e1720929775d8da3df08eeb8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49948347"
---
# <a name="idebugprogram2step"></a>IDebugProgram2::Step
Выполняет шаг.  
  
> [!NOTE]
>  Этот метод является устаревшим. Используйте [шаг](../../../extensibility/debugger/reference/idebugprocess3-step.md) метод вместо этого.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Step(   
   IDebugThread2*  pThread,  
   STEPKIND        sk,  
   STEPUNIT        step  
);  
```  
  
```csharp  
int Step(   
   IDebugThread2  pThread,  
   enum_STEPKIND  sk,  
   enum_STEPUNIT  step  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pThread`  
 [in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) , представляющий поток, в настоящее время шаг.  
  
 `sk`  
 [in] Значение из [STEPKIND](../../../extensibility/debugger/reference/stepkind.md) перечисление, указывающее тип шага.  
  
 `step`  
 [in] Значение из [STEPUNIT](../../../extensibility/debugger/reference/stepunit.md) перечисление, указывающее единицы шага (например, путем инструкцию или инструкции).  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## <a name="remarks"></a>Примечания  
 В случае любой синхронизации потоков или связи между потоками, другие потоки в программе следует запускать при отладке определенного потока.  
  
> [!WARNING]
>  В случае остановки или немедленно (синхронно) событие, чтобы не отправлять [событий](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) при обработке этого вызова; в противном случае отладчик может зависнуть.  
  
## <a name="see-also"></a>См. также  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)