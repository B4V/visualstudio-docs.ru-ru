---
title: 'CA1041: Укажите сообщение ObsoleteAttribute | Документация Майкрософт'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f67bbd93816da3bcae389493b74623f0cf4776c0
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49914727"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: укажите сообщение ObsoleteAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|Категория|Microsoft.Design|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина
 Тип или член помечен с помощью <xref:System.ObsoleteAttribute?displayProperty=fullName> атрибут, который не поддерживает его <xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName> указанное свойство.

## <a name="rule-description"></a>Описание правила
 <xref:System.ObsoleteAttribute> используется для пометки устаревшие библиотеки типов и членов. Потребители библиотеки следует избегать использования любого типа или члена, который помечен как устаревший. Это, так как он может не поддерживаться и в конечном итоге будет отсутствовать в более поздних версиях библиотеки. Если тип или член помечен с помощью <xref:System.ObsoleteAttribute> компилируется, <xref:System.ObsoleteAttribute.Message%2A> отображается свойство атрибута. Это предоставляет пользователю сведения об устаревшем типе или члене. Эти сведения обычно содержат как долго устаревший тип или член будет поддерживаться разработчиками и какой компонент для использования.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, добавьте `message` параметр <xref:System.ObsoleteAttribute> конструктор.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Не отключайте предупреждение из этого правила, так как <xref:System.ObsoleteAttribute.Message%2A> свойство предоставляет важные сведения о устаревший тип или член.

## <a name="example"></a>Пример
 В следующем примере показано устаревший член, который есть правильно объявленный <xref:System.ObsoleteAttribute>.

 [!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/cpp/FxCop.Design.ObsoleteAttributeOnMember.cpp#1)]
 [!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/cs/FxCop.Design.ObsoleteAttributeOnMember.cs#1)]
 [!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/vb/FxCop.Design.ObsoleteAttributeOnMember.vb#1)]

## <a name="see-also"></a>См. также
 <xref:System.ObsoleteAttribute?displayProperty=fullName>



