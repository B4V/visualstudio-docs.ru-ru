---
title: 'CA1031: Не перехватывайте типы общих исключений | Документация Майкрософт'
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
- CA1031
- DoNotCatchGeneralExceptionTypes
helpviewer_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
ms.assetid: cbc283ae-2a46-4ec0-940e-85aa189b118f
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2548fe0e54e57e4374f8ae92e9d43302df419aa4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49940194"
---
# <a name="ca1031-do-not-catch-general-exception-types"></a>CA1031: не перехватывайте типы общих исключений
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotCatchGeneralExceptionTypes|
|CheckId|CA1031|
|Категория|Microsoft.Design|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина
 Общие исключения, такие как <xref:System.Exception?displayProperty=fullName> или <xref:System.SystemException?displayProperty=fullName> перехватывается в `catch` инструкции или универсальной конструкции catch например `catch()` используется.

## <a name="rule-description"></a>Описание правила
 Общие исключения не должны перехватываться.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, перехватить исключение более конкретного характера или повторно выдать общее исключение в последнем операторе в `catch` блока.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Для этого правила отключать вывод предупреждений не следует. Перехват типы общих исключений может скрыть проблемы времени выполнения от пользователя библиотеки и может сделать отладку намного сложнее.

> [!NOTE]
>  Начиная с [!INCLUDE[net_v40_long](../includes/net-v40-long-md.md)], общеязыковой среды выполнения (CLR) больше не передает исключения поврежденного состояния, возникающие в операционную систему и управляемого кода, например нарушения прав доступа в [!INCLUDE[TLA#tla_mswin](../includes/tlasharptla-mswin-md.md)], для обработки в управляемом коде. Если вы хотите компиляции приложения в [!INCLUDE[net_v40_short](../includes/net-v40-short-md.md)] или более поздней версии и поддерживать обработка исключений поврежденного состояния, можно применить <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> атрибут к методу, который обрабатывает исключения поврежденного состояния.

## <a name="example"></a>Пример
 В следующем примере показано, тип, который нарушает это правило и тип, реализующий правильно `catch` блока.

 [!code-cpp[FxCop.Design.ExceptionAndSystemException#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ExceptionAndSystemException/cpp/FxCop.Design.ExceptionAndSystemException.cpp#1)]
 [!code-csharp[FxCop.Design.ExceptionAndSystemException#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ExceptionAndSystemException/cs/FxCop.Design.ExceptionAndSystemException.cs#1)]
 [!code-vb[FxCop.Design.ExceptionAndSystemException#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ExceptionAndSystemException/vb/FxCop.Design.ExceptionAndSystemException.vb#1)]

## <a name="related-rules"></a>Связанные правила
 [CA2200: следует повторно вызывать исключение для сохранения сведений о стеке](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)



