---
title: "Разрешение вопросов, связанных с исключениями: System.OutOfMemoryException | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "OutOfMemoryException - класс"
ms.assetid: eb16f008-964e-40a1-91f6-6ad25fa82d5a
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Разрешение вопросов, связанных с исключениями: System.OutOfMemoryException
Исключение <xref:System.OutOfMemoryException> возникает в случае неудачной попытки выделить память.  
  
## Полезные советы  
 **При создании массива убедитесь, что размер имеет правильное значение.**  
 Дополнительные сведения для пользователей Visual Basic см. в разделе [Массивы](/dotnet/visual-basic/programming-guide/language-features/arrays/index).  
  
 Дополнительные сведения для пользователей C\# см. в разделе [Массивы](/dotnet/csharp/programming-guide/arrays/index).  
  
 **Убедитесь в наличии достаточного объема памяти для внутренних целей и для новых управляемых объектов.**  
 При программировании на [!INCLUDE[Compact](../extensibility/includes/compact_md.md)], среда CLR генерирует это исключение, когда недостаточно памяти для внутренних целей или для новых управляемых объектов. Для того чтобы предотвратить возникновение исключения, не программируйте большие методы, которые занимают в памяти 64 и больше килобайт.  
  
## Примечания  
 Чрезмерное использование управляемой памяти обычно вызывается:  
  
-   Считыванием в память больших наборов данных.  
  
-   Созданием больших записей в кеше  
  
-   Передачей или загрузкой больших файлов.  
  
-   Чрезмерным использованием регулярных выражений или строк при синтаксическом анализе файлов.  
  
-   Чрезмерным состоянием просмотра.  
  
-   Слишком большим объёмом данных в состоянии сеанса или слишком большим количеством сеансов.  
  
 Это исключение может быть сгенерировано с дополнительным сообщением: Недостаточно свободной памяти для завершения этой операции, которое появляется при вызове метода для объекта COM, возвращающем определяемый пользователем тип, содержащий безопасный массив \(массив не фиксированного размера\). Это происходит, потому что .NET Framework. не может маршалировать поля структуры с безопасным типом массива.  
  
## См. также  
 <xref:System.OutOfMemoryException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)