---
title: Порты | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- ports
- debugging [Debugging SDK], ports
ms.assetid: 1d7f3aa7-7eff-4cab-bc53-0a566b1a9363
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f54ec931bc34f854d1c9f1a85961f5af65a56264
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49936346"
---
# <a name="ports"></a>Порты
В архитектуре отладчик *порт*:  
  
- Контейнер для набора процессов выполняется на сервере. Например порт может представлять подключение устройства на базе Windows CE с помощью последовательного кабеля или на компьютер сети без DCOM. Один особый порт, локальный порт, содержит все процессы, запущенные на локальном компьютере.  
  
- Можно идентифицировать себя по имени или идентификатора.  
  
- Можно перечислить все процессы, запущенные на порт и запуска и завершения этих процессов.  
  
- Представленный [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) интерфейс, который создается путем передачи [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) аргумент [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md).  
  
  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] предоставляет порт по умолчанию, который обрабатывает все на базе Windows процессы, машинном и управляемом. Пользовательский порт должны настраиваться для соединений с внешних устройств, которые не основаны на Windows. Чтобы предоставить такие настраиваемые порты, необходимо настроить поставщика пользовательского порта.  
  
## <a name="see-also"></a>См. также  
 [Серверы](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [Процессы](../../extensibility/debugger/processes.md)   
 [Отладчик: основные понятия](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md)   
 [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)