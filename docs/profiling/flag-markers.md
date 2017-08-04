---
title: "Маркеры флагов | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.markers.flag
ms.assetid: f3ec919e-63e5-484b-adbf-8f0e79342e75
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: 0095311f5188260bf1207e4094c1ceb87b1bbb86
ms.contentlocale: ru-ru
ms.lasthandoff: 05/13/2017

---
# <a name="flag-markers"></a>Маркеры флагов
Маркер флага представляет событие, которое произошло в определенный момент времени в приложении. Флаг может представлять различные типы событий приложения. Например, флаг может представлять момент, когда был запланирован определенный рабочий элемент или возникло исключение. Среды выполнения, такие как библиотека параллельных задач, также могут создавать флаги.  
  
## <a name="flag-importance"></a>Важность флага  
 Размер флага зависит от его важности. Как и для любого маркера, важность может быть обычной, высокой и критической.  На этом рисунке показан внешний вид маркеров по уровню важности.  
  
 ![Маркеры важности: низкая, обычная, высокая и критическая](~/profiling/media/cvmarkerimportance.png "CVMarkerImportance")  
Маркеры, показывающие важность флага  
  
## <a name="flag-category"></a>Категория флага  
 Флаг отображается в одном из пяти различных цветов в зависимости от его категории. Цвета используются повторно, если требуется больше пяти категорий. Пользователь не может выбрать цвет. Как и любой маркер, категория может быть любым целым числом. На следующем рисунке показаны цвета первых пяти категорий.  
  
 ![Пять цветов маркеров категорий](~/profiling/media/cvmarkercategory.png "CVMarkerCategory")  
Маркеры, показывающие категории  
  
## <a name="alerts"></a>Предупреждения  
 Оповещение — это флаг красного цвета, представляющий критическое событие приложения, такое как исключение.  Вот пример оповещения:  
  
 ![Маркер оповещения визуализатора параллелизма](~/profiling/media/cvmarkeralert.png "CVMarkerAlert")  
Маркер оповещения  
  
## <a name="aggregation-flags"></a>Объединяющие флаги  
 Иногда флаги отображаются так близко друг к другу в визуализаторе параллелизма, что их невозможно прорисовать по отдельности. Когда это происходит, отображается серый *объединяющий флаг*, представляющий базовые флаги. При наведении указателя мыши на один из этих значков появляется подсказка с количеством представленных базовых флагов. Чтобы просмотреть флаги, увеличьте масштаб. Если при полном увеличении все равно отображается объединяющий флаг, вы можете просмотреть базовые флаги в [отчете о маркерах](../profiling/markers-report.md).  
  
 Объединяющие флаги отображаются в различных размерах. Размер зависит от уровня важности наиболее важных флагов в объединении. На следующем рисунке объединяющие флаги показаны в порядке возрастания их важности.  
  
 ![Объединяющие флаги, показывающие четыре уровня важности](~/profiling/media/cvmarkeraggregate.png "CVMarkerAggregate")  
Объединяющие флаги по степени важности  
  
## <a name="see-also"></a>См. также  
 [Маркеры визуализатора параллелизма](../profiling/concurrency-visualizer-markers.md)   
 [Пакет SDK визуализатора параллелизма](../profiling/concurrency-visualizer-sdk.md)