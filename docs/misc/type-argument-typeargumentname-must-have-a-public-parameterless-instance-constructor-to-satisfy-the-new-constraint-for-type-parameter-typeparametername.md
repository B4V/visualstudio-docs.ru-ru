---
title: "В соответствии с ограничением New параметра типа &quot;&lt;имя_параметра_типа&gt;&quot; аргумент типа &quot;&lt;имя_аргумента_типа&gt;&quot; должен иметь публичный конструктор экземпляра, не содержащий параметров. | Microsoft Docs"
ms.custom: ""
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32083"
  - "BC32083"
helpviewer_keywords: 
  - "BC32083"
ms.assetid: 56bf25f1-375c-4b5d-9969-45eba8b3b66c
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# В соответствии с ограничением New параметра типа &quot;&lt;имя_параметра_типа&gt;&quot; аргумент типа &quot;&lt;имя_аргумента_типа&gt;&quot; должен иметь публичный конструктор экземпляра, не содержащий параметров.
Аргумент типа предоставляет в параметр типа с ограничением [Оператор New](/dotnet/visual-basic/language-reference/operators/new-operator) тип без доступного конструктора без параметров.  
  
 Список ограничений налагает требования на аргумент типа, передаваемый в параметр типа. Одно из возможных требований заключается в том, что аргумент типа должен предоставлять конструктор без параметров, к которому код создания может получить доступ. Для указания этого требования список ограничений включает ограничение `New`.  
  
 **Идентификатор ошибки:** BC32083  
  
### Исправление ошибки  
  
1.  Проверьте правильность написания имени универсального типа и имени типа в аргументе типа.  
  
2.  Выберите тип для аргумента типа, который предоставляет доступный конструктор без параметров. Вы не можете вызывать этот конкретный универсальный тип, если не можете предоставить такой аргумент типа в этот параметр типа.  
  
## См. также  
 [Универсальные типы в Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Список типов](/dotnet/visual-basic/language-reference/statements/type-list)   
 [Практическое руководство. Использование универсального класса](../Topic/How%20to:%20Use%20a%20Generic%20Class%20\(Visual%20Basic\).md)