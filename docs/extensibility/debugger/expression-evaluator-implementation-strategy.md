---
title: Стратегия реализации вычислителя выражений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expression evaluation, implementation strategy
- debug engines, implementation strategies
ms.assetid: 1bccaeb3-8109-4128-ae79-16fd8fbbaaa2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a0b60a82b9451dfa43f5cd231fd38dd32b1729ed
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233052"
---
# <a name="expression-evaluator-implementation-strategy"></a>Стратегия реализации вычислителя выражений
> [!IMPORTANT]
>  В Visual Studio 2015 таким образом, реализации вычислители выражений является устаревшим. Сведения о реализации вычислители выражений CLR, см. в разделе [вычислители выражений CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) и [образец средства оценки выражений управляемый](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Один из способов создания вычислитель выражений (EE) является сначала реализация минимальный код, необходимый для отображения локальных переменных в **"Локальные"** окна. Полезно понимать, что каждая строка в **"Локальные"** окне отображается имя, тип и значение локальной переменной, и все три представленных [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) объекта. Имя, тип и значение локальной переменной получается из `IDebugProperty2` , вызвав его [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) метод. Дополнительные сведения о том, как для отображения локальных переменных в **"Локальные"** окно, см. в разделе ["Локальные" Отображение](../../extensibility/debugger/displaying-locals.md).  
  
## <a name="discussion"></a>Обсуждение  
 Возможная реализация последовательность начинается с реализации [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md). [Проанализировать](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) и [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) методы должны быть реализованы для отображения локальных переменных. Вызов `IDebugExpressionEvaluator::GetMethodProperty` возвращает `IDebugProperty2` , представляющий метод: то есть [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) объекта. Сами методы не отображаются в **"Локальные"** окна.  
  
 [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) метод должен быть реализован рядом. Модуль отладки (DE) вызывает этот метод, чтобы получить список локальных переменных и аргументов, передавая `IDebugProperty2::EnumChildren` `guidFilter` аргумент `guidFilterLocalsPlusArgs`. `IDebugProperty2::EnumChildren` вызовы [EnumArguments](../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) и [EnumLocals](../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md), объединение результатов в одного перечисления. См. в разделе [отображения локальных переменных](../../extensibility/debugger/displaying-locals.md) для получения дополнительных сведений.  
  
## <a name="see-also"></a>См. также  
 [Реализация вычислителя выражений](../../extensibility/debugger/implementing-an-expression-evaluator.md)   
 [Отображение локальных переменных](../../extensibility/debugger/displaying-locals.md)