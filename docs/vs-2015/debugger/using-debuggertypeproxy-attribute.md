---
title: Использование атрибута DebuggerTypeProxy | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- attributes [C#], debugger
- DebuggerTypeProxyAttribute class
- DebuggerTypeProxy attribute
ms.assetid: 943f3bb1-993e-4800-a47e-0af78b063014
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f7b404253c2425a64fd2a9ad4bb53943e033d8e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49898841"
---
# <a name="using-debuggertypeproxy-attribute"></a>Использование атрибута DebuggerTypeProxy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

DebuggerTypeProxyAttribute] (assetId:///T:System.Diagnostics.DebuggerTypeProxyAttribute?qualifyHint=False & autoUpgrade = True) Указывает учетную запись-посредник или заместителя, типа и меняет способ тип отображается в окнах отладчика. При просмотре переменной, которая имеет учетную запись-посредник, прокси заменяет исходный тип в **отображения**. Окно переменных отладчика отображает только открытые члены прокси-типа. Закрытые члены не отображаются.  
  
 Данный атрибут может применяться к:  
  
- Структуры  
  
- Классы  
  
- Сборки  
  
  Класс прокси-типа должен иметь конструктор, принимающий аргумент типа, который будет заменен прокси. Отладчик создает новый экземпляр класса прокси-типа всякий раз, когда требуется отобразить переменную конечного типа. Это может сказываться на производительности. Поэтому не следует выполнять в конструкторе больше действий, чем это действительно необходимо.  
  
  Для снижения потерь производительности вычислитель выражений не проверяет атрибуты при отображении прокси-типа до тех пор, пока тип не будет развернут щелчком по символу "+" в окне отладчика или путем применения атрибута <xref:System.Diagnostics.DebuggerBrowsableAttribute>. Таким образом, не следует применять атрибуты к самому типу отображения. Атрибуты можно и нужно применять в основной части типа отображения.  
  
  Прокси-тип рекомендуется делать закрытым вложенным классом внутри класса, к которому применяется атрибут. В этом случае он может легко получить доступ к внутренним членам.  
  
  Если атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> используется на уровне сборки, параметр `Target` указывает тип, который заменяется прокси.  
  
  Пример использования этого атрибута вместе с <xref:System.Diagnostics.DebuggerDisplayAttribute> и <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, см. в разделе[использование атрибута DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md).  
  
## <a name="using-generics-with-debuggertypeproxy"></a>Использование универсальных типов с атрибутом DebuggerTypeProxy  
 Поддержка универсальных типов ограничена. Для C# атрибут `DebuggerTypeProxy` поддерживает только открытые типы. Открытый тип (также называемый "не сконструированным" типом) — это универсальный тип, экземпляр которого создается без аргументов для параметров типа. Закрытые типы (также называемые сконструированными типами) не поддерживаются.  
  
 Синтаксис для открытого типа выглядит следующим образом:  
  
 `Namespace.TypeName<,>`  
  
 Этот синтаксис необходимо использовать при использовании универсального типа в качестве целевого типа в атрибуте `DebuggerTypeProxy`. Атрибут `DebuggerTypeProxy` предположит параметры типа самостоятельно.  
  
 Дополнительные сведения об открытых и закрытых типах в C# см. в разделе [спецификации языка C#](http://msdn.microsoft.com/library/e5d5a5cc-636b-4bff-b9c8-a8edc6207c22), откройте раздел 20.5.2 и закрытые типы.  
  
 В Visual Basic синтаксис для открытых типов не поддерживается, поэтому данный способ для Visual Basic не подходит. Вместо этого необходимо использовать строковое представление имени открытого типа.  
  
 `"Namespace.TypeName'2"`  
  
## <a name="see-also"></a>См. также  
 [Использование атрибута DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)   
  [Повышение эффективности отладки с помощью атрибутов просмотра отладчика](http://msdn.microsoft.com/library/72bb7aa9-459b-42c4-9163-9312fab4c410)



