---
title: '&#39;вернуть&#39; инструкции за пределами функции | Документация Майкрософт'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT1018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 03568f9f-5f4f-4a10-a738-9a73f3832b9e
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07b633c87dc11b291a5a5783f8121b2a368996d6
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49846522"
---
# <a name="39return39-statement-outside-of-function"></a>&#39;вернуть&#39; инструкции за пределами функции
Вы использовали `return` оператор в глобальной области кода. `return` Оператор должен отображаться только в теле функции.  
  
 Вызов функции с помощью `()` оператор — это выражение. Все выражения имеют значения; `return` инструкция используется для указания значения, возвращенного функцией. Выглядит следующим образом:  
  
```  
  
return [ expression ];  
```  
  
 Когда `return` выполняется инструкция, *выражение* вычисляется и возвращается в качестве значения функции. Если отсутствует выражение, **неопределенный** возвращается.  
  
 Выполнение функции останавливается, когда `return` инструкция выполняется, даже при наличии других инструкций, по-прежнему осталось в теле функции. Исключением из этого правила является Если **возвращают** оператор находится внутри **попробуйте** блока, и есть соответствующая **наконец** блока, код в  **Наконец** блок будет выполняться до выполнения возврата функцией.  
  
 Если функция возвращает, так как она достигает конца тела функции без выполнения `return` инструкции, возвращаемое значение **неопределенный** значение (это означает, что результатом функции не может использоваться как часть более крупного выражения ).  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалить `return` инструкции от основной части кода (глобальная область).  
  
## <a name="see-also"></a>См. также  
 [Оператор return](../../javascript/reference/return-statement-javascript.md)   
 [Объект функции](../../javascript/reference/function-object-javascript.md)   
 [Свойство caller (Function)](../../javascript/reference/caller-property-function-javascript.md)