---
title: "Практическое руководство. Определение набора правил для управляемого кода в решении для нескольких проектов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.codeanalysis.propertypages.solution"
ms.assetid: 92dc3250-a010-4396-b515-f03a0b30cd2a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Определение набора правил для управляемого кода в решении для нескольких проектов
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

По умолчанию, все управляемые проекты решения подчиняются *набору правил* анализа кода "Минимальные правила и рекомендации корпорации Майкрософт".  Наборы правил, назначенные проекту решения, можно менять в диалоговом окне свойств решения.  
  
> [!NOTE]
>  По умолчанию, анализ кода проекта, как этап построения, не выполняется.  Дополнительные сведения о включении анализа кода в качестве этапа построения см. в разделе [Практическое руководство. Настройка анализа кода для проекта управляемого кода](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md).  
  
### Определение набора правил для нескольких проектов в решении с управляемым кодом  
  
1.  В методе [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)].  [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] или [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)] откроют решение.  
  
2.  В меню **Анализ** щелкните **Настройка анализа кода для решения**.  
  
3.  При необходимости, разверните узел **Общие свойства**, затем выберите **Параметры анализа кода**.  
  
4.  Набор правил можно задать для одного или нескольких проектов.  
  
    -   Чтобы задать набор правил для отдельного проекта, щелкните имя проекта.  
  
    -   Чтобы задать набор правил для нескольких проектов, щелкайте имена проектов, удерживая нажатой клавишу CTRL.  
  
    -   Чтобы выбрать все проекты решения, щелкните список проектов, удерживая нажатой клавишу SHIFT.  
  
5.  Щелкните поле проекта **Набор правил**, а затем выберите имя набора правил, который следует применить.