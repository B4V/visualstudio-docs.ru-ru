---
title: Представление "Ядра" | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.view.cores
helpviewer_keywords:
- Concurrency Visualizer, Cores View
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 09103357e207712b8678b2de9c9573cc14331dbf
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49283235"
---
# <a name="cores-view"></a>Представление "Ядра"
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

В представление "Ядра" демонстрируется сопоставление выполнения потока с логическими ядрами процессора. При написании серверных приложений это представление может помочь оптимизировать производительность кэша за счет использования сходства потоков или управления пулом потоков. Оно также помогает изучать случаи, когда использование сходства потоков может усугубить проблему переходов между ядрами. Представление "Ядра" состоит из двух частей — графа и легенды.  
  
 В графе отображаются логические ядра по оси Y и время по оси X. Каждый поток в графе имеет уникальный цвет, поэтому можно отслеживать его перемещение между ядрами с течением времени. Можно отфильтровать потоки в графе, выбрав их в области легенды.  
  
 Область легенды содержит запись для каждого цвета в графе. Каждая запись показывает цвет потока и имя, количество переключений контекста между ядрами, общее количество переключений контекста и процент переключений контекста между ядрами. Легенда сортируется по количеству переключений контекста между ядрами в порядке убывания. В ней указаны только потоки, которые выполнялись в течение указанного диапазона.  Список обновляется при масштабировании или панорамировании.  
  
## <a name="see-also"></a>См. также  
 [Визуализатор параллелизма](../profiling/concurrency-visualizer.md)   
 [Представление "Использование"](../profiling/utilization-view.md)   
 [Представление потоков](../profiling/threads-view-parallel-performance.md)



