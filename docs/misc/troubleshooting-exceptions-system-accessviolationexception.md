---
title: "Разрешение вопросов, связанных с исключениями: System.AccessViolationException | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "System.AccessViolationException - исключение"
  - "AccessViolationException - класс"
ms.assetid: 7f09315d-8aad-4ab1-8b5e-21a8c97f6c14
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Разрешение вопросов, связанных с исключениями: System.AccessViolationException
Исключение <xref:System.AccessViolationException> возникает при попытке чтения или записи в защищенную область памяти.  
  
## Полезные советы  
 Убедитесь, что память, в которую производится доступ, была выделена.  
 Автоматическое управление памятью — это одна из служб, которые предоставляет среда CLR. Может потребоваться использовать управляемый код, чтобы воспользоваться преимуществами этой службы. Для получения дополнительной информации см. [Автоматическое управление памятью](../Topic/Automatic%20Memory%20Management.md).  
  
 Убедитесь, что память, в которую производится доступ, не была повреждена.  
 Если несколько операций чтения или записи произошли по неправильным указателям, память может быть повреждена.  
  
### Примечания  
 Нарушение прав доступа случается в неуправляемом или небезопасном коде при попытке чтения или записи в память, которая не была выделена или к которой нет доступа. Не все операции чтения или записи по неправильным указателям приводят к нарушениям прав доступа, поэтому нарушение прав доступа обычно указывает, что таких операций было несколько и что память может быть повреждена.  
  
 В управляемом коде все ссылки являются либо допустимыми, либо пустыми. Любая операция, которая пытается сослаться на пустую ссылку в проверяемом коде вызывает исключение <xref:System.NullReferenceException>.  
  
 Нарушение прав доступа, возникающее в небезопасном управляемом коде, может быть выражено как исключение <xref:System.NullReferenceException> или <xref:System.AccessViolationException>, в зависимости от платформы.  
  
 Нарушения прав доступа в неуправляемом коде, передаваясь вверх к управляемому коду всегда помещаются \("оборачиваются"\) в исключение <xref:System.AccessViolationException>.  
  
## См. также  
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [Управление памятью. Примеры](../Topic/Memory%20Management:%20Examples.md)   
 [Автоматическое управление памятью](../Topic/Automatic%20Memory%20Management.md)