---
title: "CA2211: неконстантные поля должны быть скрыты | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2211"
  - "NonConstantFieldsShouldNotBeVisible"
helpviewer_keywords: 
  - "CA2211"
  - "NonConstantFieldsShouldNotBeVisible"
ms.assetid: e1e42c40-0acd-4312-af29-70133739a304
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 13
---
# CA2211: неконстантные поля должны быть скрыты
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|NonConstantFieldsShouldNotBeVisible|  
|CheckId|CA2211|  
|Категория|Microsoft.Usage|  
|Критическое изменение|Критическое изменение|  
  
## Причина  
 Открытое или защищенное поле не является константным и доступным только для чтения.  
  
## Описание правила  
 Для статических полей, которые не являются константными и доступными только для чтения, невозможно обеспечить потокобезопасность.  Доступ к подобным полям должен тщательно контролироваться, и для синхронизации доступа к такому объекту класса требуются дополнительные методы программирования.  Поскольку все это требует особых навыков, которыми трудно овладеть, и тестирования, также создающего свои трудности, статические поля лучше использовать для хранения неизменяемых данных.  Это правило применяется к библиотекам; приложения не должны предоставлять поля.  
  
## Устранение нарушений  
 Чтобы устранить нарушение данного правила, сделайте статическое поле константным или доступным только для чтения.  Если это невозможно, измените структуру типа, чтобы использовать альтернативный механизм, например потокобезопасное свойство, которое управляет потокобезопасным доступом к базовому полю.  Следует понять, что такие проблемы, как конфликт блокировок или взаимоблокировки, могут отрицательно сказаться на производительности или поведении библиотеки.  
  
## Отключение предупреждений  
 Отключение предупреждений о нарушении данного правила безопасно в том случае, если разрабатывается приложение и, следовательно, осуществляется полный контроль над доступом к типу, содержащему статическое поле.  Создателям библиотек не следует отключать подобные предупреждения; использование неконстантных статических полей может затруднить правильное использование библиотеки для разработчиков.  
  
## Пример  
 В следующем примере показан тип, который нарушает данное правило.  
  
 [!code-vb[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/VisualBasic/ca2211-non-constant-fields-should-not-be-visible_1.vb)]
 [!code-cs[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/CSharp/ca2211-non-constant-fields-should-not-be-visible_1.cs)]