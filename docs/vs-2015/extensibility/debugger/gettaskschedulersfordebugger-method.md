---
title: Метод GetTaskSchedulersForDebugger | Документация Майкрософт
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
- GetTaskSchedulersForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c763499a053119340ca6827d3190aa4163af4fe0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49229961"
---
# <a name="gettaskschedulersfordebugger-method"></a>Метод GetTaskSchedulersForDebugger
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Получает массив всех <xref:System.Threading.Tasks.TaskScheduler> объектов, которые активны в текущий момент.  
  
 **Пространство имен:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Сборка:** mscorlib (в mscorlib.dll)  
  
 Так как не удается получить доступ к внутреннему элементу из .NET Framework, следующий синтаксис предоставляется общего промежуточного языка (CIL).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Массив всех <xref:System.Threading.Tasks.TaskScheduler> объектов, которые активны в текущий момент в этом <xref:System.AppDomain>.  
  
## <a name="remarks"></a>Примечания  
 Этот метод не является потокобезопасным и не должны использоваться параллельно с другими экземплярами <xref:System.Threading.Tasks.TaskScheduler>. Он должен вызываться из отладчика, только в том случае, если отладчик приостановил всех остальных потоков.  
  
## <a name="see-also"></a>См. также  
 [Класс TaskScheduler](../../extensibility/debugger/taskscheduler-class-internal-members.md)

