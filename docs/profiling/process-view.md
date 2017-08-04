---
title: "Представление &quot;Процесс&quot; | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.view.process
helpviewer_keywords:
- performance tools reports, process view
- Process view
- performance tools, process view
- Profiling Tools,process view
- Profiling Tools,process report
ms.assetid: 6d4e2a5d-9f17-4ece-a6f1-75836e1fc382
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: a1f55111b5fcc8c36a5bfc8f86d25354fa89d8b8
ms.lasthandoff: 02/22/2017

---
# <a name="process-view"></a>Представление "Процесс"
В представлении процесса отображаются данные о профилировании для процессов и потоков, которые выполнялись во время сеанса профилирования.  
  
 Процессы упорядочены по имени. Потоки указываются как дочерние узлы создавших их процессов. Потоки именуются по запустивших их функциям или по метке **[ntdll.dll]** при отсутствии доступных символов.  
  
 Чтобы добавить или удалить столбцы, щелкните правой кнопкой мыши в представлении и выберите **Добавить или удалить столбцы**. Кроме того, щелкнув имя столбца, можно сортировать данные. Дополнительные сведения см. в статье [How to: Customize Report View Columns](../profiling/how-to-customize-report-view-columns.md) (Практическое руководство. Настройка столбцов представлений отчета).  
  
 Столбцы в представлении процесса являются одинаковыми для данных, которые созданы с помощью методов выборки и инструментирования, а также для данных, которые включают данные памяти .NET. В следующей таблице описаны значения столбцов.  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Уникальный идентификатор**|Созданный профилировщиком идентификатор, уникальным образом определяющий процесс или поток.|  
|**Идентификатор**|Созданный системой идентификатор процесса или потока.|  
|**Имя**|Имя процесса или потока.|  
|**Время начала**|Количество миллисекунд или циклов процессора от начала профилирования до запуска процесса или потока.|  
|**Время окончания**|Количество миллисекунд или циклов процессора от начала профилирования до завершения процесса или потока.|  
  
## <a name="see-also"></a>См. также  
 [Представления данных метода выборки](../profiling/profiler-sampling-method-data-views.md)   
 [Представления данных метода инструментирования](../profiling/instrumentation-method-data-views.md)   
 [Представления данных в памяти .NET](../profiling/dotnet-memory-data-views.md)