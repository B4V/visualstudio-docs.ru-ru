---
title: IDebugObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugObject
helpviewer_keywords:
- IDebugObject interface
ms.assetid: 05cd8bf4-c9ee-4b49-b782-2263c33067d6
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9aaf72e0e4d47bc938efb78639f2d47d3ae1fffa
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49201751"
---
# <a name="idebugobject"></a>IDebugObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

> [!IMPORTANT]
>  В Visual Studio 2015 таким образом, реализации вычислители выражений является устаревшим. Сведения о реализации вычислители выражений CLR, см. в разделе [вычислители выражений CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) и [управляемых образец средства оценки выражений](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Этот интерфейс представляет объект, который создает связыватель для инкапсуляции значения символов и выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
IDebugObject : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Примечания для разработчиков  
 Вычислитель выражений реализует этот интерфейс для представления объекта.  
  
## <a name="notes-for-callers"></a>Заметки о вызывающих объектов  
 Этот интерфейс является базовым классом для всех объектов, которые использует средство оценки выражений в проанализированного выражения. Он возвращается вызовом [привязать](../../../extensibility/debugger/reference/idebugbinder-bind.md) метод. [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) получает более специализированных интерфейсов из этого интерфейса.  
  
## <a name="methods-in-vtable-order"></a>Методы в порядке таблицы Vtable  
 В следующей таблице показаны методы `IDebugObject`.  
  
|Метод|Описание|  
|------------|-----------------|  
|[GetSize](../../../extensibility/debugger/reference/idebugobject-getsize.md)|Возвращает размер объекта.|  
|[GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)|Возвращает значение объекта как ряд последовательных байтов.|  
|[SetValue](../../../extensibility/debugger/reference/idebugobject-setvalue.md)|Задает значение объекта из последовательных последовательность байтов.|  
|[SetReferenceValue](../../../extensibility/debugger/reference/idebugobject-setreferencevalue.md)|Задает значения этого объекта ссылки.|  
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugobject-getmemorycontext.md)|Получает контекст памяти, представляющий адрес значения объекта.|  
|[GetManagedDebugObject](../../../extensibility/debugger/reference/idebugobject-getmanageddebugobject.md)|Создает копию управляемого объекта в адресном пространстве для обработчика отладки.|  
|[IsNullReference](../../../extensibility/debugger/reference/idebugobject-isnullreference.md)|Проверяет, является ли этот объект является пустой ссылкой.|  
|[IsEqual](../../../extensibility/debugger/reference/idebugobject-isequal.md)|Сравнивает объект данному.|  
|[IsReadOnly](../../../extensibility/debugger/reference/idebugobject-isreadonly.md)|Определяет, является ли этот объект только для чтения.|  
|[IsProxy](../../../extensibility/debugger/reference/idebugobject-isproxy.md)|Определяет, является ли объект прозрачный прокси-сервер.|  
  
## <a name="remarks"></a>Примечания  
 Средство оценки выражений использует этот интерфейс в качестве базового класса для представления объектов в дерево синтаксического анализа.  
  
## <a name="requirements"></a>Требования  
 Заголовок: ee.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы оценки выражения](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)   
 [Bind](../../../extensibility/debugger/reference/idebugbinder-bind.md)

