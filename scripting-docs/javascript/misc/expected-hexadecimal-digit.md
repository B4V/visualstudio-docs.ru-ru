---
title: Ожидаемый шестнадцатеричная цифра | Документация Майкрософт
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
- VS.WebClient.Help.SCRIPT1023
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 67a86df7-49f9-43cb-99c6-99b1a427827a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9e29131c4ecf4f476a30da94ec67676d6bea347
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49836181"
---
# <a name="expected-hexadecimal-digit"></a>Ожидалась шестнадцатеричная цифра
Вы создали неверные escape-последовательности Юникода. Escape-последовательности Юникода начинаются с \u, следуют ровно четыре шестнадцатеричные цифры (не больше и не меньше). Шестнадцатеричные цифры в Юникоде может содержать только цифры 0 – 9, прописные буквы A-F и строчные буквы a-f. Ниже приведен пример неправильно сформирован escape-последовательность Юникода.  
  
```JavaScript  
z = "\u1A5F";  
```  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что ваш шестнадцатеричных цифр Юникода начинаются с \u, содержит только цифры 0 – 9, прописные буквы A-F, строчные буквы a – f; которые сгруппированы в четыре цифры.  
  
    > [!NOTE]
    >  Если вы хотите использовать \u литеральный текст в строке, а затем укажите две черты подряд - (\\\u) — один для первого.  
  
## <a name="see-also"></a>См. также  
 [Типы данных](../../javascript/data-types-javascript.md)