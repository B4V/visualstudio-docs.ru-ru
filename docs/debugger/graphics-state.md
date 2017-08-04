---
title: "Состояние графики | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.graphics.statewindow"
ms.assetid: 97e7757e-c372-4626-8149-99a81367a0e1
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Состояние графики
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Окно «Состояние» в диагностике графики Visual Studio помогает понять состояние графики, активное на момент возникновения текущего события, такого как вызов Draw.  
  
## Общие сведения об окне «Состояние»  
 Окно состояния собирает сведения о состоянии, которые влияют на отрисовку, и представляет их иерархически в одном месте.  Сведения, представленные в окне состояния, могут отличаться в зависимости от версии Direct3D, которую использует ваше приложение.  
  
### Представления состояний  
 Вы можете просмотреть таблицу состояний несколькими разными способами:  
  
|Просмотр|Описание|  
|--------------|--------------|  
|Представление входного состояния API|Это представление представляет состояние в виде расположения объектов Direct3D, составляющих данное состояние.|  
|Представление входного логического состояния|Это представление представляет состояние в виде логической схемы, которая не отражает объекты Direct3D, составляющие данное состояние.|  
|Представление закрепленного состояния|Вместо иерархии представление закрепленного состояния представляет элементы закрепленного состояния в виде плоского списка полных имен.  Это представление позволяет просматривать большое число элементов состояния из разных пакетов состояния на небольшом числе строк.|  
  
##### Изменение представления состояния  
  
-   В верхней левой части окна «Состояние», сразу под строкой заголовка, нажмите кнопку, соответствующую тому стилю представления состояния, который вы хотите использовать.  
  
    -   **Отображение представления входного состояния API**  
  
    -   **Показать представление логического состояния**  
  
    -   **Показать представление закрепленного состояния**  
  
> [!IMPORTANT]
>  Необходимо закрепить состояние в представлениях **Показать входное состояние API** или **Показать логическое состояние**, чтобы оно отображалось в области **Показать представление закрепленного состояния**.  
  
### Формат таблицы состояний  
 Окно «Состояние» содержит несколько столбцов данных.  
  
|Столбец|Описание|  
|-------------|--------------|  
|Имя|Имя элемента состояния.  Если этот элемент представляет пакет состояний, элемент можно развернуть, чтобы отобразить его.<br /><br /> В состояниях **Представление входного состояния API** и **Представление логического состояния** имена отображаются с отступом, чтобы показать иерархическую связь между состояниями.<br /><br /> В состоянии **Представление закрепленного состояния** полные имена отображаются в виде плоского списка.|  
|Значение|Значение элемента состояния.|  
|Тип|Тип элемента состояния.|  
  
### Измененное состояние  
 Обычно состояние графики между вызовами Draw изменяется постепенно, а неправильное изменение состояния является причиной многих проблем отрисовки.  Чтобы помочь вам найти состояние, которое было изменено со времени предыдущего вызова Draw, измененное состояние помечается звездочкой и выделяется красным цветом — это относится не только к самому состоянию, но и к его родительскому элементу состояния. Таким образом, вы можете легко обнаружить измененное состояние на высоком уровне, а затем детализировать подробности.  
  
### Состояние закрепления  
 Поскольку многие приложения визуализируют схожие объекты последовательно, изменяя набор состояния, иногда бывает удобно закрепить изменяющиеся состояния, чтобы можно было наблюдать, как они изменяются при переходе от одного вызова Draw к другому.  
  
 Это также может быть полезно, если вы определили, что источник проблемы связан с изменением в определенном состоянии.  
  
##### Закрепление состояния на месте  
  
1.  Найдите нужное вам состояние в окне «Состояние».  Для поиска интересующих вас подробностей может потребоваться развернуть состояние более высокого уровня.  
  
2.  Наведите курсор на состояние, которое вас интересует.  Слева от элемента состояния отображается значок закрепления.  
  
3.  Выберите этот значок для закрепления элемента состояния на месте.