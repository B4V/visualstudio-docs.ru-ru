---
title: IDebugCoreServer3 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer3
helpviewer_keywords:
- IDebugCoreServer3 interface
ms.assetid: 51f5f41b-a5a4-4df0-a703-41f3d1811d7f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5066521dbed42790d508becc1a3591dff3ae559d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
ms.locfileid: "31108535"
---
# <a name="idebugcoreserver3"></a>IDebugCoreServer3
Этот интерфейс предоставляет доступ к информации о сервере, в которой выполняется процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
IDebugCoreServer3 : IDebugCoreServer2  
```  
  
## <a name="notes-for-implementers"></a>Примечания для разработчиков  
 Visual Studio реализует этот интерфейс.  
  
## <a name="notes-for-callers"></a>Примечания для вызывающих объектов  
 Используйте [QueryInterface](/cpp/atl/queryinterface) получить этот интерфейс из [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) интерфейса. Вызов [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md) также может возвращать этот интерфейс. Этот интерфейс используется чаще всего supplier настраиваемый порт для запуска программы на сервере (локально или удаленно).  
  
## <a name="methods-in-vtable-order"></a>Методы в порядке таблицы Vtable  
 В дополнение к методам на [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) интерфейс, этот интерфейс реализует следующие методы:  
  
|Метод|Описание|  
|------------|-----------------|  
|[GetServerName](../../../extensibility/debugger/reference/idebugcoreserver3-getservername.md)|Возвращает имя сервера.|  
|[GetServerFriendlyName](../../../extensibility/debugger/reference/idebugcoreserver3-getserverfriendlyname.md)|Извлекает версию понятное имя сервера|  
|[EnableAutoAttach](../../../extensibility/debugger/reference/idebugcoreserver3-enableautoattach.md)|Сообщает определенные отладчики выполнить присоединение к процессу автоматически при запуске этих процессов.|  
|[DiagnoseWebDebuggingError](../../../extensibility/debugger/reference/idebugcoreserver3-diagnosewebdebuggingerror.md)|Получает код ошибки, когда автоматическое присоединение завершается с ошибкой.|  
|[CreateInstanceInServer](../../../extensibility/debugger/reference/idebugcoreserver3-createinstanceinserver.md)|Создает экземпляр модуля отладки на сервере.|  
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugcoreserver3-queryislocal.md)|Возвращает флаг, указывающий, является ли сервер на том же компьютере, что и вызывающий объект.|  
|[GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)|Получает значение, указывающее протокол, используемой для связи с сервером.|  
|[DisableAutoAttach](../../../extensibility/debugger/reference/idebugcoreserver3-disableautoattach.md)|Отключает все автоматического присоединения параметров все модули отладки, которые известны этого сервера.|  
  
## <a name="remarks"></a>Примечания  
 Получает поставщика пользовательских порта [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) интерфейса во время вызова [событие](../../../extensibility/debugger/reference/idebugportevents2-event.md). `IDebugCoreServer3` Интерфейса можно получить из этого интерфейса.  
  
## <a name="requirements"></a>Требования  
 Заголовок: msdbg.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>См. также  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)