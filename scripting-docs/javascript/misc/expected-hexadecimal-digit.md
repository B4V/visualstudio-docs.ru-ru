---
title: "Ожидалась шестнадцатеричная цифра | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.WebClient.Help.SCRIPT1023"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 67a86df7-49f9-43cb-99c6-99b1a427827a
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# Ожидалась шестнадцатеричная цифра
Вы создали неверную escape\-последовательность Юникода.  Escape\-последовательность Юникода начинается со знаков \\u, за которыми следуют четыре шестнадцатеричных знака \(не больше и не меньше\).  Шестнадцатеричные знаки могут содержать только цифры от 0 до 9, буквы верхнего регистра от A до F и буквы нижнего регистра от a до f.  В следующем примере показана правильно построенная escape\-последовательность Юникода.  
  
```javascript  
z = "\u1A5F";  
```  
  
### Исправление ошибки  
  
-   Убедитесь, что шестнадцатеричные знаки Юникода начинаются с символов \\u и содержат только цифры 0\-9, буквы верхнего регистра A\-F и буквы нижнего регистра a\-f, а также включают 4 разряда.  
  
    > [!NOTE]
    >  Если необходимо использовать в строке собственно текст \\u, используйте две обратных косых черты \(\\\\u\) — первая для отмены действия косой черты.  
  
## См. также  
 [Типы данных](../../javascript/data-types-javascript.md)