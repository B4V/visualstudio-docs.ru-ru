---
title: Справочник по API (Отладка Visual Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], API reference
ms.assetid: e4e429da-3667-41f7-9158-a8207d13e91a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 97d5aa6fc92457557493005389d129993d38e099
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49839444"
---
# <a name="api-reference-visual-studio-debugging"></a>Справочник API (отладка Visual Studio)
В справочном разделе включает в себя общие сведения об API, направляющей, демонстрирует синтаксис и использование для всех элементов API, а также целый ряд примеров кода. Все ссылки перечислены в алфавитном порядке по категориям.  
  
 В следующей таблице приведены распространенные `HRESULT` значения, возвращаемые методами.  
  
|name|Описание|Значение|  
|----------|-----------------|-----------|  
|S_OK|Выполнено.|0x00000000|  
|E_UNEXPECTED|Непредвиденная ошибка.|0x8000FFFF|  
|E_NOTIMPL|Не реализовано.|0x80004001|  
|E_OUTOFMEMORY|Недостаточно памяти для завершения операции.|0x8007000E|  
|E_INVALIDARG|Один или несколько аргументов являются недопустимыми.|0x80070057|  
|E_NOINTERFACE|Интерфейс не поддерживается.|0x80004002|  
|E_POINTER|Недопустимый указатель.|0x80004003|  
|E_HANDLE|Недопустимый дескриптор.|0x80070006|  
|E_ABORT|Операция прервана.|0x80004004|  
|E_FAIL|Непредвиденная ошибка.|0x80004005|  
|E_ACCESSDENIED|Ошибка доступа.|0x80070005|  
  
> [!NOTE]
>  Когда [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] отладки метод возвращает `S_OK`, предполагается, что все указатели параметра являются допустимыми, то есть проверка не проводится на out параметр указателей при `S_OK` возвращается.  
> 
> [!NOTE]
>  Недопустимый или `NULL` [параметров out] может привести к сбою в работе интегрированной среды разработки.  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы](../../../extensibility/debugger/reference/interfaces-visual-studio-debugging.md)   
 [Перечисления](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Структуры и объединения](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [Вспомогательные пакеты SDK для отладки](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Расширяемость отладчика Visual Studio](../../../extensibility/debugger/visual-studio-debugger-extensibility.md)