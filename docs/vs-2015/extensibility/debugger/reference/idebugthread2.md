---
title: IDebugThread2 | Документация Майкрософт
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
- IDebugThread2
helpviewer_keywords:
- IDebugThread2 interface
ms.assetid: 221b4b1b-4a26-466e-bc29-5eff800fab13
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cdd6d15d5ac5547502b1b7dbc4c4f60a0a0e5750
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49189030"
---
# <a name="idebugthread2"></a>IDebugThread2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Этот интерфейс представляет поток, выполняемый в приложении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
IDebugThread2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Примечания для разработчиков  
 Модуль отладки (DE) реализует этот интерфейс для представления потока выполнения в одной программе.  
  
## <a name="notes-for-callers"></a>Заметки о вызывающих объектов  
 Вызовите [GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md) для получения этого интерфейса, представляющий текущего активного потока.  
  
 Этот интерфейс также используется при создании запроса точки останова (см. в разделе [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)).  
  
 Этот интерфейс также возвращается при разрешении точки останова границу или ошибки (см. в разделе [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) и [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)).  
  
## <a name="methods-in-vtable-order"></a>Методы в порядке таблицы Vtable  
 В следующей таблице показаны методы `IDebugThread2`.  
  
|Метод|Описание|  
|------------|-----------------|  
|[EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)|Извлекает список кадров стека для данного потока.|  
|[GetName](../../../extensibility/debugger/reference/idebugthread2-getname.md)|Возвращает имя потока.|  
|[SetThreadName](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)|Задает имя потока.|  
|[GetProgram](../../../extensibility/debugger/reference/idebugthread2-getprogram.md)|Возвращает программу, в котором выполняется поток.|  
|[CanSetNextStatement](../../../extensibility/debugger/reference/idebugthread2-cansetnextstatement.md)|Определяет, можно ли установить следующий оператор к контексту заданного стека кадра и код.|  
|[SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)|Задает следующий оператор к контексту заданного стека кадра и кода.|  
|[GetThreadId](../../../extensibility/debugger/reference/idebugthread2-getthreadid.md)|Получает идентификатор потока системы.|  
|[Suspend](../../../extensibility/debugger/reference/idebugthread2-suspend.md)|Приостанавливает поток.|  
|[Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)|Возобновляет работу потока.|  
|[GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)|Получает свойства, описывающие поток.|  
|[GetLogicalThread](../../../extensibility/debugger/reference/idebugthread2-getlogicalthread.md)|Получает логический поток, связанный с этой физическом потоке.|  
  
## <a name="remarks"></a>Примечания  
 Поскольку одного физического потока могут выполняться в нескольких программ, более чем на одном `IDebugThread2` из более чем одной программы может представлять том же физическом потоке.  
  
 При возникновении исключения или точка останова, событие передается с помощью [событий](../../../extensibility/debugger/reference/idebugeventcallback2-event.md). Один из аргументов в этот метод имеет `IDebugThread2` интерфейс, представляющий текущий поток. [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) используется для получения [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) интерфейс для текущего кадра стека.  
  
## <a name="requirements"></a>Требования  
 Заголовок: msdbg.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>См. также  
 [Базовых интерфейсов](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Событие](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [GetThread](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)

