---
title: "Пошаговое руководство. Отсутствие объектов вследствие заливки вершин | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e42b54a0-8092-455c-945b-9ecafb129d93
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Пошаговое руководство. Отсутствие объектов вследствие заливки вершин
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

В данном пошаговом руководстве показано, как с помощью средств диагностики графики [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] исследовать объект, который отсутствует из\-за ошибки, возникшей на этапе шейдера вершин.  
  
 В данном пошаговом руководстве рассмотрены следующие задачи:  
  
-   Использование **списка событий графики** для обнаружения возможных источников проблем.  
  
-   Проверка результата вызова API Direct3D `DrawIndexed` с помощью окна **Этапы графического конвейера**.  
  
-   Проверка шейдеров вершин с помощью **отладчика HLSL**.  
  
-   Поиск источника неправильных констант HLSL с помощью **стека вызовов событий графики**.  
  
## Сценарий  
 Одна из распространенных причин отсутствия объекта в трехмерном приложении — это когда шейдер вершин преобразует вершины объекта неправильным или неожиданным способом. Например, объект может быть масштабирован до очень небольшого размера или преобразован таким образом, что оказывается позади камеры, а не перед ней.  
  
 В этом сценарии при запуске приложения для тестирования фон отрисовывается так, как ожидалось, однако один из объектов не отображается. С помощью диагностики графики можно записать данные о проблеме в журнал графики, чтобы можно было выполнить отладку приложения. Проблема в приложении выглядит следующим образом:  
  
 ![Объект не виден.](~/debugger/graphics/media/gfx_diag_demo_missing_object_shader_problem.png "gfx\_diag\_demo\_missing\_object\_shader\_problem")  
  
## Исследование  
 С помощью средств диагностики графики можно загрузить файл журнала графики для проверки кадров, захваченных в ходе теста.  
  
#### Анализ кадра в журнале графики  
  
1.  В [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] загрузите журнал графики, содержащий кадр, на котором видно, что объект отсутствует. Появляется новая вкладка журнала графики в [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. В верхней части этой вкладки находится вывод целевого объекта отрисовки для выбранного кадра. В нижней части находится **Список кадров**, в котором каждый захваченный кадр отображается как эскиз.  
  
2.  В **списке кадров** выберите кадр, который демонстрирует, что объект не отображается. Однобуферная прорисовка обновляется, и в ней отображается выбранный кадр. В этом сценарии вкладка журнала графики выглядит следующим образом:  
  
     ![Документ журнала графики в Visual Studio](../debugger/media/gfx_diag_demo_missing_object_shader_step_1.png "gfx\_diag\_demo\_missing\_object\_shader\_step\_1")  
  
 После выбора кадра, который демонстрирует проблему, можно приступать к диагностике с использованием окна **Список событий графики**.**Список событий графики** содержит все вызовы API Direct3D, которые были выполнены для отрисовки активного кадра, например вызовы API для настройки состояния устройства, для создания и обновления буферов, а также для рисования объектов, которые присутствуют в кадре. Многие типы вызовов представляют интерес, так как при надлежащей работе приложения часто \(но не всегда\) происходит соответствующее изменение в целевом объекте отрисовки. Это касается вызовов Draw, Dispatch, Copy или Clear. Особенно интересны вызовы Draw, так как каждый из них представляет геометрию, отрисованную приложением \(вызовы Dispatch также могут отрисовывать геометрию\).  
  
 Так как известно, что отсутствующий объект не отрисовывается в целевом объекте отрисовки \(в данном случае\), однако остальная часть сцены отрисовывается как надо, можно воспользоваться окном **Список событий графики** в сочетании с окном **Этапы графического конвейера**, чтобы определить, какой из вызовов Draw соответствует геометрии отсутствующего объекта. В окне **Этапы графического конвейера** показана геометрия, отправленная в каждый вызов Draw независимо от влияния на однобуферную прорисовку. По мере продвижения по вызовам Draw этапы конвейера обновляются для отображения геометрии, связанной с конкретным вызовом, а вывод целевого объекта отрисовки обновляется для отображения состояния целевого объекта отрисовки по завершении вызова.  
  
#### Поиск вызова Draw для отсутствующей геометрии  
  
1.  Откройте окно **Список событий графики**. На панели инструментов **Диагностика графики** выберите **Список событий**.  
  
2.  Откройте окно **Этапы графического конвейера**. На панели инструментов **Диагностика графики** выберите **Этапы конвейера**.  
  
3.  Просматривая вызовы Draw в окне **Список событий графики**, перейдите в окно **Этапы графического конвейера** для отсутствующего объекта. Чтобы упростить эту задачу, введите Draw в поле **Поиск** в верхнем правом углу окна **Список событий графики**. Список будет отфильтрован и будет содержать только события, в названиях которых присутствует слово «Draw».  
  
     В окне **Этапы графического конвейера** этап **Сборщик входных данных** показывает геометрию объекта перед его преобразованием, а этап **Шейдер вершин** показывает тот же объект после преобразования. В этом сценарии известно, что обнаружен отсутствующий объект при его отображении на этапе **Сборщик входных данных** и что ничего не отображается на этапе **Шейдер вершин**.  
  
    > [!NOTE]
    >  Если другие этапы геометрии — например, этапы шейдера поверхности, шейдера доменов или шейдера геометрии — обрабатывают объект, они могут быть причиной проблемы. Обычно проблема связана с самым ранним этапом, в котором результат не отображается или отображается непредвиденным образом.  
  
4.  Остановитесь, когда достигнете вызова Draw, соответствующего отсутствующему объекту. В этом сценарии в окне **Этапы графического конвейера** видно, что геометрия была передана в GPU \(о чем говорит наличие эскиза сборщика входных данных\), однако она не отображается в целевом объекте отрисовки, так как произошла ошибка на этапе шейдера вершин \(об этом говорит эскиз шейдера вершин\).  
  
     ![Событие DrawIndexed и его результат в конвейере](~/debugger/graphics/media/gfx_diag_demo_missing_object_shader_step_2.png "gfx\_diag\_demo\_missing\_object\_shader\_step\_2")  
  
 Убедившись, что приложение передало вызов Draw для геометрии отсутствующего объекта, и обнаружив, что проблема возникает на этапе шейдера вершин, можно использовать отладчик HLSL для проверки шейдера вершин и узнать, что случилось с геометрией объекта. Отладчик HLSL можно использовать для проверки состояния переменных HLSL при выполнении, пошагового выполнения кода HLSL и указания точек останова для помощи в диагностике проблемы.  
  
#### Проверка шейдера вершин  
  
1.  Запустите отладку этапа шейдера вершин. В окне **Этапы графического конвейера** в разделе этапа **Шейдер вершин** нажмите кнопку **Начать отладку**.  
  
2.  Так как этап **Сборщик входных данных** предоставляет хорошие данные в шейдер вершин, а этап **Шейдер вершин** не производит никаких выходных данных, следует изучить структуру вывода шейдера вершин, `output`. При пошаговом выполнении кода HLSL его можно более внимательно изучить, чтобы узнать, когда изменяется `output`.  
  
3.  При первом изменении `output` член `worldPos` записывается.  
  
     ![Значение "output.worldPos" оказывается допустимым](~/debugger/graphics/media/gfx_diag_demo_missing_object_shader_step_4.png "gfx\_diag\_demo\_missing\_object\_shader\_step\_4")  
  
     Так как его значение кажется разумным, пошаговое выполнение кода продолжается до следующей строки, которая изменяет `output`.  
  
4.  При следующем изменении `output` член `pos` записывается.  
  
     ![Значение "output.pos" было обнулено](~/debugger/graphics/media/gfx_diag_demo_missing_object_shader_step_5.png "gfx\_diag\_demo\_missing\_object\_shader\_step\_5")  
  
     На этот раз значение члена `pos` — все нули, и это кажется подозрительным. Далее нужно определить, как случилось так, что `output.pos` имеет все нули в качестве значения.  
  
5.  Можно заметить, что `output.pos` получает значение из переменной, которая называется `temp`. В предыдущей строке видно, что значение `temp` является результатом умножения его предыдущего значение на константу, которая называется `projection`. Кажется, что подозрительное значение `temp` является результатом такого умножения. При наведении указателя мыши на `projection` можно заметить, что его значением также являются все нули.  
  
     ![Матрица проекций содержит недопустимое преобразование](~/debugger/graphics/media/gfx_diag_demo_missing_object_shader_step_6.png "gfx\_diag\_demo\_missing\_object\_shader\_step\_6")  
  
     В этом сценарии анализ показывает, что подозрительное значение `temp`, скорее всего, вызвано его умножением на `projection`, и так как `projection` — константа, в которой должна находиться матрица проекции, становится понятно, что она не должна содержать все нули.  
  
 После определения того, что константа HLSL `projection`, переданная в шейдер приложением, — вероятная причина проблемы, следующий шаг — поиск места в исходном коде приложения, где заполняется буфер констант. Найти это место можно с помощью **стека вызовов событий графики**.  
  
#### Поиск места задания константы в исходном коде приложения  
  
1.  Откройте окно **Стек вызовов событий графики**. На панели инструментов **Диагностика графики** выберите **Стек вызовов событий графики**.  
  
2.  Перейдите в стек вызовов в исходном коде приложения. В окне **Стек вызовов событий графики** выберите самый верхний вызов, чтобы узнать, заполняется ли там буфер констант. Если нет, продолжайте перемещаться вверх по стеку вызовов, пока не найдете место, где он заполняется. В этом сценарии обнаружено, что буфер констант заполняется \(с помощью Direct3D API `UpdateSubresource`\) выше по стеку вызовов в функции с именем `MarbleMaze::Render` и что его значение берется из объекта буфера констант с именем `m_marbleConstantBufferData`:  
  
     ![Код, устанавливающий постоянный буфер объекта](~/debugger/graphics/media/gfx_diag_demo_missing_object_shader_step_7.png "gfx\_diag\_demo\_missing\_object\_shader\_step\_7")  
  
    > [!TIP]
    >  При одновременной отладке приложения можно установить точку останова в этом месте, и она будет достигнута при отрисовке следующего кадра. Это позволяет проверить члены `m_marbleConstantBufferData`, чтобы убедиться, что значение члена `projection` равно всем нулям при заполнении буфера констант.  
  
 Найдя расположение, где заполняется буфер констант, и обнаружив, что его значения берутся из переменной `m_marbleConstantBufferData`, следующим шагом выясните, где значение члена `m_marbleConstantBufferData.projection` равно всем нулям. Можно использовать функцию **Найти все ссылки**, чтобы быстро выполнить поиск кода, меняющего значение `m_marbleConstantBufferData.projection`.  
  
#### Поиск места задания члена проекции в исходном коде приложения  
  
1.  Найдите ссылки на `m_marbleConstantBufferData.projection`. Откройте контекстное меню константы `m_marbleConstantBufferData` и выберите пункт **Найти все ссылки**.  
  
2.  Чтобы перейти к строке в исходном коде приложения, где изменен член `projection`, выберите эту строку в окне **Результаты поиска символа**. Так как первый результат, который изменяет член проекции, может не быть причиной проблемы, возможно, придется изучить несколько областей исходного кода приложения.  
  
 После нахождения расположения, где задается значение `m_marbleConstantBufferData.projection`, можно изучить окружающий исходный код для определения источника неправильного значения. В этом сценарии обнаружено, что в качестве значения `m_marbleConstantBufferData.projection` задана локальная переменная с именем `projection` до инициализации значения, указанного кодом `m_camera->GetProjection(&projection);` на следующей строке.  
  
 ![Проекция шарика задается до инициализации](~/debugger/graphics/media/gfx_diag_demo_missing_object_shader_step_9.png "gfx\_diag\_demo\_missing\_object\_shader\_step\_9")  
  
 Чтобы устранить проблему, переместите строку кода, которая устанавливает значение `m_marbleConstantBufferData.projection` после строки, которая инициализирует значение локальной переменной `projection`.  
  
 ![Исправленный исходный код C&#43;&#43;](~/debugger/graphics/media/gfx_diag_demo_missing_object_shader_step_10.png "gfx\_diag\_demo\_missing\_object\_shader\_step\_10")  
  
 Внеся исправления в код, можно заново собрать его и еще раз запустить приложение, чтобы убедиться, что проблема с отрисовкой решена.  
  
 ![Объект появился.](~/debugger/graphics/media/gfx_diag_demo_missing_object_shader_resolution.png "gfx\_diag\_demo\_missing\_object\_shader\_resolution")