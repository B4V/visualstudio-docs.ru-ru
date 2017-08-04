---
title: "Практическое руководство. Моделирование трехмерного ландшафта | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f779b1fd-82a9-4a11-8ab7-c1c9caabc883
caps.latest.revision: 17
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
caps.handback.revision: 17
---
# Практическое руководство. Моделирование трехмерного ландшафта
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

В этом документе показано, как использовать Средство редактирования моделей для создания трехмерной модели ландшафта.  
  
 Этот документ демонстрирует эти действия:  
  
-   Добавление элементов к сцене  
  
-   Выбор граней и точек  
  
-   Выбор преобразований  
  
-   Использование средства **Subdivide face**  
  
-   Обрамление объектов на поверхности разработки  
  
## Создание модели объемной поверхности  
 Можно создать объемную поверхность, разделив плоскость для создания дополнительных поверхностей, а затем обработать их вершины для создания интересных особенностей поверхности.  
  
 В итоге модель должна выглядеть так:  
  
 ![Трехмерная сцена, показывающая модель поверхности](~/designers/media/digit-terrain-model.png "Digit\-Terrain\-Model")  
  
 Перед началом убедитесь, что окна **Properties** и **Toolbox** отображаются.  
  
#### Создание трехмерной модели ландшафта  
  
1.  Создание трехмерной модели для работы.  Сведения о том, как добавить модель в ваш проект, смотрите в разделе "Начало работы" в [Редактор моделей](../designers/model-editor.md).  
  
2.  Добавьте поверхность к сцене.  В разделе **Панель элементов** в области **Фигуры** выберите **Плоскость** и переместите ее на поверхность разработки.  
  
    > [!TIP]
    >  Чтобы сделать объект плоскости более простым для работы, поместите его в Поверхность разработки.  В режиме **Select** выберите объект поверхности, а затем на панели инструментов Редактора моделей нажмите кнопку **Frame Object**.  
  
3.  Войдите в режим выбора поверхности.  На панели инструментов Редактора модели выберите **Select Face**.  
  
4.  Разделите плоскость.  В режиме выделения поверхностей выберите поверхность один раз, чтобы активировать ее для выделения, после чего выберите ее повторно, чтобы выделить ее только начертание.  На панели инструментов Редактора модели выберите **Subdivide face**.  Это действие добавляет на поверхность новые вершины, разбивающие грань на четыре одинаковые по размеру части.  
  
5.  Создайте еще несколько разделений.  Сохраняя выбор новых граней, выберите **Subdivide face** еще два раза.  Это создает всего 64 сторон.  Путем создания нескольких подразделений, можно предоставить территории еще больше деталей.  
  
6.  Войдите в режим выбора точки.  На панели инструментов Редактора модели выберите **Select Point**.  
  
7.  Измените точку для создания особенности рельефа.  В режиме выбора точек выберите одну из точек, а затем на панели инструментов Редактора моделей выберите инструмент **Translate**.  Поле, представляющее то, что точка отображается в области конструктора.  Используйте зеленую стрелку, чтобы переместить окно и таким образом изменить высоту точки.  Повторите этот шаг для различных точек, чтобы создать интересные подробности рельефа.  
  
    > [!TIP]
    >  Можно выбрать несколько точек одновременно, чтобы изменить их в единообразном способом.  
  
 Модель местности завершена.  Ниже показана финальная версия модели с примененным к ней затенением Фонга:  
  
 ![Трехмерная сцена, показывающая модель поверхности](~/designers/media/digit-terrain-model.png "Digit\-Terrain\-Model")  
  
 Можно использовать эту модель ландшафта, чтобы продемонстрировать эффект шейдера градиента, описанный в [Практическое руководство. Создание основанного на геометрии шейдера градиента](../designers/how-to-create-a-geometry-based-gradient-shader.md).  
  
## См. также  
 [Редактор моделей](../designers/model-editor.md)