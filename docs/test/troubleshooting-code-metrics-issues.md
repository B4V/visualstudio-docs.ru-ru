---
title: "Устранение неполадок, связанных с метриками кода | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
caps.latest.revision: 4
author: "erickson-doug"
ms.author: "douge"
manager: "douge"
caps.handback.revision: 4
---
# Устранение неполадок, связанных с метриками кода
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Во время сбора метрик кода могут возникать некоторые из перечисленных ниже проблем.  
  
-   [Изменения в вычислениях сложности кода Visual Studio 2010](#Changes_in_Visual_Studio_2010_code_complexity_calculations)  
  
##  <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a> Изменения в вычислениях сложности кода Visual Studio 2010  
 В перечисленных ниже ситуациях метрика сложности кода, вычисленная в [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] для определенной функции, может отличаться от метрики, вычисленной для той же функции в предыдущих версиях [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].  
  
-   Функция содержит один или несколько блоков catch.  В предыдущих версиях [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] блоки catch в вычислении не учитывались.  В [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] сложность каждого блока catch добавлялась к сложности функции.  
  
-   Функция содержит оператор switch \(Select Case в VB\).  Различия в компиляторе [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] и компиляторе предыдущих версий может привести к различиям в коде MSIL для некоторых операторов switch, содержащих операторы case с проходом при невыполнении условия.  
  
## См. также  
 [Оценка сложности и удобства сопровождения управляемого кода](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)