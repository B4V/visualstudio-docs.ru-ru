---
title: 'CA1005: не используйте слишком много параметров в универсальных типах'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
helpviewer_keywords:
- AvoidExcessiveParametersOnGenericTypes
- CA1005
ms.assetid: 372b2f28-5c59-4815-9753-6c65b2bb3589
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e65427aecb2d4ecc135480d23834fdc07a413b05
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49850130"
---
# <a name="ca1005-avoid-excessive-parameters-on-generic-types"></a>CA1005: не используйте слишком много параметров в универсальных типах

|||
|-|-|
|TypeName|AvoidExcessiveParametersOnGenericTypes|
|CheckId|CA1005|
|Категория|Microsoft.Design|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина
 Видимый извне универсальный тип имеет более двух параметров типа.

## <a name="rule-description"></a>Описание правила
 Чем больше параметров типов содержит универсальный тип, тем сложнее знать и запоминать, что представляет каждый параметр типа. Обычно ситуация очевидна при использовании одного параметра типа, как и в `List<T>`и в некоторых случаях с двумя параметрами типа, как и в `Dictionary<TKey, TValue>`. Если существует более двух параметров типа, сложность становится слишком большим для большинства пользователей (например, `TooManyTypeParameters<T, K, V>` в C# или `TooManyTypeParameters(Of T, K, V)` в [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, измените структуру использовать не более двух параметров типа.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Не отключайте предупреждение из этого правила, если просто необходимо использовать более двух параметров типа. Использование универсальных типов в синтаксисе, который прост для понимания и использования сокращает время, необходимое для обучения и увеличивает скорость внедрения новых библиотек.

## <a name="related-rules"></a>Связанные правила
 [CA1010: коллекции должны реализовывать универсальный интерфейс](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: не объявляйте статические элементы в универсальных типах](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: не следует раскрывать универсальные списки](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: не вкладывайте универсальные типы в сигнатуры членов](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: универсальные методы должны предоставлять параметр типа](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: используйте экземпляры обработчика универсальных событий](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: используйте универсальные объекты, если это уместно](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>См. также
 [Универсальные шаблоны](/dotnet/csharp/programming-guide/generics/index)