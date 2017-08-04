---
title: "Схемы зависимостей: Ссылки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.teamarch.layerdiagram.layerexplorer.artifactlink
- vs.teamarch.layerdiagram.layerexplorer.artifactlink.properties
- vs.teamarch.layerdiagram.diagram
- vs.teamarch.UMLModelExplorer.layerdiagram
- vs.teamarch.layerdiagram.layerexplorer
- vs.teamarch.layerdiagram.shapes.properties
- vs.teamarch.layerdiagram.toolbox
helpviewer_keywords:
- architecture, dependency diagrams
- dependency diagrams
- diagrams - modeling, layer
- constraints, architectural
ms.assetid: f26c986c-1e79-420e-b29a-a283e6d8a71d
caps.latest.revision: 33
author: alexhomer1
ms.author: ahomer
manager: douge
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
translationtype: Machine Translation
ms.sourcegitcommit: fd26c504273cae739ccbeef5e406891def732985
ms.openlocfilehash: 74829877befa9f48988d42e04a58e2a418e7d82b
ms.lasthandoff: 02/22/2017

---
# <a name="dependency-diagrams-reference"></a>Схемы зависимостей: Справочник
В Visual Studio можно использовать *Диаграмма зависимостей* для визуализации высокоуровневой логической архитектуры системы. Диаграмма зависимостей организует физические артефакты системы в логические, абстрактные группы, называемые *слои*. Слои описывают основные компоненты системы или задачи, выполняемые этими артефактами. Каждый слой может также содержать вложенные слои, описывающие более подробные задачи.  
  
 Чтобы узнать, какие версии Visual Studio поддерживают эту функцию, см. раздел [поддержка версий для инструментов моделирования и архитектуры](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Между слоями можно установить предполагаемые или существующие зависимости. Эти зависимости, представленные в виде стрелок, показывают, какие слои могут использовать или в настоящее время используют функциональные возможности, представленные другими слоями. Организуя системы в уровни, описывающие различные роли и функции, диаграмма зависимостей может помочь упростить понять, использовать повторно и обслуживать код.  
  
 С помощью схемы зависимостей помогают выполнять следующие задачи:  
  
-   представлять существующую или предполагаемую логическую архитектуру системы;  
  
-   выявлять конфликты между существующим кодом и предполагаемой архитектурой;  
  
-   визуализировать влияние изменений на предполагаемую архитектуру при рефакторинге, обновлении или развитии системы;  
  
-   дополнительно контролировать предполагаемую архитектуру в процессе разработки и обслуживания кода за счет добавления проверки операций возврата и построения.  
  
 В этом разделе описаны элементы, которые можно использовать на схеме зависимостей. Более подробные сведения о том, как создать и схем зависимостей см. в разделе [схемы зависимостей: рекомендации по](../modeling/layer-diagrams-guidelines.md). Дополнительные сведения о шаблонах слоев посетите [сайт шаблоны и рекомендации &](http://go.microsoft.com/fwlink/?LinkId=145794).  
  
## <a name="reading-dependency-diagrams"></a>Чтение схем зависимостей  
 ![Элементы на схемах зависимостей](~/modeling/media/uml_layerrefreading.png "UML_LayerRefReading")  
  
 Следующая таблица описывает элементы, которые можно использовать на схеме зависимостей.  
  
|**Фигуры**|**Элемент**|**Описание**|  
|---------------|-----------------|---------------------|  
|1|**Слой**|Логическая группа физических артефактов в системе. Артефактами могут быть пространства имен, проекты, классы, методы и т. п.<br /><br /> Для просмотра связанных со слоем артефактов, откройте контекстное меню слоя и выберите **Просмотр ссылок** открыть **обозреватель слоев**.<br /><br /> Дополнительные сведения см. в разделе [обозреватель слоев](#Explorer).<br /><br /> -   **Запрещенные зависимости пространства имен** -указывает, что артефакты, связанные с этим слоем, не могут зависеть от указанного пространства имен.<br />-   **Запрещенные пространства имен** -указывает, что артефакты, связанные с этим слоем, не должны принадлежать указанному пространству имен.<br />-   **Обязательные пространства имен** -указывает, что артефакты, связанные с этим слоем должны принадлежать к одному из указанных пространств имен.|  
|2|**Зависимости**|Указывает, что один слой может использовать функции другого слоя, но не наоборот.<br /><br /> -   **Направление** -указывает направление зависимости.|  
|3|**Двунаправленная зависимость**|Указывает, что один слой может использовать функции другого слоя и наоборот.<br /><br /> -   **Направление** -указывает направление зависимости.|  
|4|**Комментарий**|Используется для добавления общих примечаний к схеме или ее элементам.|  
|5|**Добавить комментарий для связи**|Используется для связи комментариев с элементами на схеме.|  
  
##  <a name="a-nameexplorera-layer-explorer"></a><a name="Explorer"></a>Обозреватель слоев  
 Каждый слой можно связать с артефактами в решении, например с проектами, классами, пространствами имен, файлами проекта и другими частями программного обеспечения. Число на слое обозначает количество связанных с этим слоем артефактов. Число артефактов в слое следует толковать с учетом следующих факторов.  
  
-   Если слой связан с артефактом, содержащим другие артефакты, но слой не связан с другими артефактами напрямую, то число включает только связанный артефакт. Однако для анализа в ходе проверки слоя включаются другие артефакты.  
  
     Например, если слой связан с одним пространством имен, то число связанных артефактов равно 1, даже если пространство имен содержит классы. Если слой также связан с каждым классом в пространстве имен, то число будет включать эти связанные классы.  
  
-   Если слой содержит другие слои, связанные с артефактами, то слой-контейнер также связан с этими артефактами, даже если число в слое-контейнере не включает эти артефакты.  
  
 Дополнительные сведения о связывании слоев и артефактов см. в разделах:  
  
-   [Схемы зависимостей: рекомендации](../modeling/layer-diagrams-guidelines.md)  
  
-   [Создание схем зависимостей в коде](../modeling/create-layer-diagrams-from-your-code.md)  
  
#### <a name="to-examine-the-linked-artifacts"></a>Просмотр связанных артефактов  
  
-   На схеме зависимостей, откройте контекстное меню для одного или нескольких слоях и выберите **Просмотр ссылок**.  
  
     **Обозреватель слоев** открывает и показаны артефакты, связанные с выбранными уровнями. **Обозреватель слоев** содержит столбец, показывающий свойства ссылок на артефакты.  
  
    > [!NOTE]
    >  Если отображаются не все эти свойства, разверните **обозреватель слоев** окна.  
  
    |**Столбец в обозревателе слоев**|**Описание**|  
    |----------------------------------|---------------------|  
    |**Категории**|Вид артефакта, например класс, пространство имен, исходный файл и т. д.|  
    |**Слой**|Связанный с артефактом слой|  
    |**Поддержка проверки**|Если **True**, то процесс проверки слоев убедитесь, что проект соответствует зависимостям к или из данного элемента.<br /><br /> Если **False**, то связь не участвует в процессе проверки уровня.<br /><br /> Дополнительные сведения см. в разделе [схемы зависимостей: рекомендации по](../modeling/layer-diagrams-guidelines.md).|  
    |**Идентификатор**|Ссылка на связанный артефакт|  
  
## <a name="see-also"></a>См. также  
 [Создание моделей для приложения](../modeling/create-models-for-your-app.md)
