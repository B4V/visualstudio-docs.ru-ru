---
title: 'Ошибка: Смешанном режиме отладки для x64 процессов поддерживается только в том случае, если с помощью Microsoft .NET Framework 4 или более поздней версии | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: b1e7159c67ab104156f2dccd6d89413594ded33c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49874414"
---
# <a name="error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-net-framework-4-or-greater"></a>Ошибка: отладка в смешанном режиме для процессов x64 поддерживается только при использовании платформы Microsoft .NET Framework 4 или выше
Для отладки смеси управляемого и неуправляемого кода в 64-разрядном процессе необходимо использовать версию 4 платформы [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Отладка в смешанном режиме для 64-разрядных процессов при использовании версий [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], предшествующих версии 4, не поддерживается.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Выполните одно из следующих действий.  
  
  - Обновите [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] до версии 4.  
  
  - Постройте для отладки 32-разрядную версию приложения.  
  
## <a name="see-also"></a>См. также  
 [Remote Debugging](../debugger/remote-debugging.md)