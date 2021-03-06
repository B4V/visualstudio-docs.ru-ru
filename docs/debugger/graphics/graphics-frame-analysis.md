---
title: Анализ кадров графики | Документация Майкрософт
ms.custom: ''
ms.date: 02/09/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.frameanalysis
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e0ae541830adab222b07d1f16ce99e4957e380e5
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49838105"
---
# <a name="graphics-frame-analysis"></a>Анализ кадров графики
Используйте анализ кадров в анализаторе графики Visual Studio, чтобы анализировать и оптимизировать производительность отрисовки в приложениях или играх, использующих Direct3D.  

## <a name="frame-analysis"></a>Анализ кадров  
 Функция анализа кадров использует для диагностики данные из файла журнала графики, применяя ее для получения сводной информации о производительности отрисовки. Информация о производительности не записывается в журнал во время захвата. Она создается позднее во время анализа кадров с помощью событий синхронизации и сбора статистики при воспроизведении кадра. Такой подход имеет ряд преимуществ в сравнении с записью информации о производительности во время захвата.  
  
- Анализ кадров позволяет получать усредненные результаты для нескольких воспроизведений одного кадра, что обеспечивает статистически достоверные данные производительности.  
  
- Анализ кадров позволяет получать информацию о производительности для конфигураций оборудования и устройств, отличных от тех, где были захвачены данные.  
  
- Анализ кадров позволяет получать новые сводки производительности от ранее захваченных данных — например, при драйверы GPU были оптимизированы или предоставляют дополнительные возможности отладки.  
  
  Помимо этих преимуществ, с помощью анализа кадров также можно изменять способ отрисовки кадра во время воспроизведения. Таким образом можно получать информацию о том, как эти изменения могут повлиять на производительность отрисовки приложения. С помощью этой информации можно выбрать наиболее подходящую из возможных стратегий оптимизации, не применяя их все, чтобы захватить данные и сравнить результаты самостоятельно.  
  
  Хотя анализ кадров в первую очередь предназначен для повышения производительности отрисовки, он может быть не менее полезен для повышения качества изображения при заданном уровне производительности или для снижения энергопотребления GPU.  
  
  Для демонстрации того, что можно сделать анализ кадров для вашего приложения, вы можете посмотреть [анализ кадров графики Visual Studio](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool) видео на канале Channel 9.  
  
## <a name="using-frame-analysis"></a>Использование анализа кадров  
 Прежде чем использовать анализ кадров, необходимо захватить графические данные из работающего приложения, так же как при использовании любого другого инструмента анализатора графики. Затем в окне документа (.vsglog) журнала графики выберите **анализ кадров** вкладки.  
  
 ![Выберите вкладку "Анализ кадров"](media/pix_frame_analysis_select_tab.png "pix_frame_analysis_select_tab")  
  
 По завершении анализа выводятся результаты. В верхней части вкладки анализа кадров находятся временная шкала и сводная таблица. В нижней части находятся таблицы с подробными данными. Если во время воспроизведения произошли ошибки или были получены предупреждения, сводная информация о них выводится над временной шкалой. Переходя по ссылкам в этой области, можно узнать больше об ошибках и предупреждениях.  
  
### <a name="interpreting-results"></a>Интерпретация результатов  
 Интерпретируя результаты для каждого варианта, можно получить полезную информацию о производительности и особенностях отрисовки приложения. Дополнительные сведения о вариантах отрисовки см. в разделе [варианты](#Variants) далее в этой статье.  
  
 Некоторые результаты непосредственно указывают на то, как вариант влияет на производительность отрисовки.  
  
- Если вариант "Билинейная фильтрация текстур" показал прирост производительности, то использование билинейной фильтрации текстур в приложении приведет к такому же приросту производительности.  
  
- Если вариант "Окно просмотра 1 x 1" показал прирост производительности, то уменьшение размеров целевых объектов отрисовки в приложении повысит производительность отрисовки.  
  
- Если вариант "Сжатие текстур BC" показал прирост производительности, то использование сжатия текстур BC в приложении приведет к такому же приросту производительности.  
  
- Если вариант 2 x MSAA имеет почти такую же производительность, что и вариант 0 x MSAA, можно включить вариант 2 x MSAA в приложении, чтобы повысить качество отрисовки без снижения производительности.  
  
  Другие результаты могут содержать менее явные указания на производительность приложения.  
  
- Если вариант "Окно просмотра 1 x 1" показывает очень значительный прирост производительности, возможно, скорость заполнения в приложении выше возможной. Если этот вариант не показывает прироста производительности, возможно, приложение обрабатывает слишком много вершин.  
  
- Если вариант "Формат целевого объекта отрисовки с глубиной цвета 16 бит" показывает значительный прирост производительности, возможно, приложение потребляет слишком много пропускной способности памяти.  
  
- Если вариант "Половинные/четвертные размеры текстур" показывает значительный прирост производительности, возможно, текстуры занимают слишком много памяти, используют слишком много пропускной способности или используют кэш текстур неэффективно. Если этот вариант не сказывается на производительности, возможно, использование более крупных, подробных текстур не снизит производительность.  
  
  Если доступны аппаратные счетчики, вы можете использовать их для сбора очень подробной информации о том, почему производительность отрисовки приложения ухудшается. Все функционального уровня 9.2 и выше устройства поддерживают запросы перекрытия глубины (**пикселей перекрыто** счетчика) и метки времени. Могут быть доступны и другие аппаратные счетчики, если изготовитель GPU реализовал их и предоставил доступ к ним посредством драйвера. Их можно использовать для уточнения причины результатов, отображаемых в сводной таблице. Например, установив процент пикселей, которые были перекрыты при выполнении тесты глубины, можно определить, является ли превышение негативным фактором.  
  
### <a name="timeline-and-summary-table"></a>Временная шкала и сводная таблица  
 По умолчанию временная шкала и сводная таблица отображаются, а другие разделы свернуты.  
  
#### <a name="timeline"></a>Временная шкала  
 На временной шкале показано время выполнения вызовов Draw относительно друг друга. Так как более длинные полоски соответствуют более длительному выполнению вызовов Draw, с их помощью можно определить наиболее затратные по времени вызовы в кадре. Если захваченный кадр содержит очень большое число вызовов Draw, несколько вызовов Draw объединяются в одну полоску, длина которой соответствует суммарному времени выполнения вызовов.  
  
 ![На временной шкале отображаются действия&#45;вызывать расходы. ](media/pix_frame_analysis_timeline.png "pix_frame_analysis_timeline")  
  
 Чтобы увидеть, какому событию вызова Draw соответствует полоска, наведите на нее указатель. При выборе полоски список событий синхронизируется с этим событием.  
  
#### <a name="table"></a>Таблица  
 В таблице с числами под временной шкалой показана производительность каждого варианта отрисовки для каждого вызова Draw относительно способа отрисовки по умолчанию в приложении. Каждый столбец соответствует отдельному варианту отрисовки, а каждая строка представляет отдельный вызов Draw, указанный в самом левом столбце. Отсюда можно перейти по ссылке к событию в окне "Список событий графики".  
  
 ![Сводная таблица с отображением различных вариантов. ](media/pix_frame_analysis_summary.png "pix_frame_analysis_summary")  
  
 Во втором слева столбце сводной таблицы показано базовое время отрисовки приложения, то есть время выполнения вызова Draw с помощью варианта отрисовки, используемого в приложении по умолчанию. В остальных столбцах показана относительная производительность каждого варианта отрисовки в процентах от базового показателя, что позволяет легко видеть, улучшилась ли производительность. Если значение превышает 100 процентов, вызов выполнялся дольше, чем при базовом варианте, то есть производительность снизилась. Если значение меньше 100 процентов, вызов выполнялся быстрее, то есть производительность возросла.  
  
 Значения абсолютного базового времени и относительного времени для вариантов отрисовки на самом деле являются средними значениями, полученными в результате нескольких вызовов (по умолчанию 5). Усреднение позволяет обеспечить достоверность и согласованность данных. Наведя указатель на ячейку в таблице, можно узнать минимальное, максимальное, среднее и центральное значения времени, полученные при выполнении данного вызова Draw с помощью данного варианта отрисовки. Также отображается базовое время.  
  
#### <a name="hot-draw-calls"></a>"Горячие" вызовы Draw  
 Для привлечения внимания к вызовам Draw, которые занимают большую часть общего времени отрисовки или могут выполняться необычно медленно по причинам, которых можно избежать, строка, содержащая такие "горячие" вызовы Draw, выделяется красным цветом, если ее собственное базовое время более чем на одно стандартное отклонение превышает среднее базовое время всех вызовов Draw в кадре.  
  
 ![Этот вызов DrawIndexed имеет варианты "Горячий" и "холодные". ](media/pix_frame_analysis_hot_calls.png "pix_frame_analysis_hot_calls")  
  
#### <a name="statistical-significance"></a>Статистическая значимость  
 Для привлечения внимания к вариантам отрисовки, имеющим наибольшую важность, при анализе кадров определяется статистическая значимость каждого из вариантов отрисовки. Значимые варианты выделяются полужирным шрифтом. Варианты, повышающие производительность, выделяются зеленым цветом, а снижающие производительность — красным. Результаты, не имеющие статистической значимости, имеют обычный шрифт.  
  
 ![Статистическая релевантность варианта вызова рисования](media/pix_frame_analysis_summary_stats.png "pix_frame_analysis_summary_stats")  
  
 Для определения статистической значимости анализ кадров использует [Стьюдента t тест](http://www.wikipedia.org/wiki/Student%27s_t-test).  
  
### <a name="details-table"></a>Таблица подробных сведений  
 Под сводной таблицей находится таблица подробных сведений, которая по умолчанию свернута. Ее содержимое зависит от аппаратной платформы компьютера воспроизведения. Сведения о поддерживаемых аппаратных платформах см. в разделе [аппаратной поддержки](#HardwareSupport).  
  
#### <a name="platforms-that-do-not-support-hardware-counters"></a>Платформы, не поддерживающие аппаратные счетчики  
 Большинство платформ не полностью поддерживают аппаратные счетчики GPU. К ним относятся все GPU, предлагаемые в настоящее время компаниями Intel, AMD и nVidia. Если аппаратные счетчики для сбора данных отсутствуют, отображается только одна таблица подробных сведений, которая содержит среднее абсолютное время для всех вариантов.  
  
 ![Таблица сведений и некоторые варианты воспроизведения. ](media/pix_frame_analysis_details.png "pix_frame_analysis_details")  
  
#### <a name="platforms-that-support-hardware-counters"></a>Платформы, поддерживающие аппаратные счетчики  
 Для платформ, поддерживающих аппаратные счетчики GPU, например на основе микросхемы SOC nVidia T40 и всех микросхем SOC Qualcomm, отображаются несколько таблиц подробных сведений (по одной для каждого варианта). Данные каждого доступного счетчика собираются для каждого варианта отрисовки и отображаются в собственной таблице подробных сведений.  
  
 ![Аппаратные счетчики отображаются в том случае, когда это возможно. ](media/pix_frame.png "pix_frame")  
  
 Данные аппаратных счетчиков позволяют получить очень подробное представление о поведении конкретных аппаратных платформ для каждого вызова Draw, что может помочь вам точно установить причины узких мест производительности.  
  
> [!NOTE]
>  Разные аппаратные платформы поддерживают разные счетчики — никаких стандартов нет. Доступные счетчики и предоставляемые ими данные определяются исключительно изготовителем GPU.  
  
### <a name="marker-regions-and-events"></a>Области маркеров и события  
 Анализ кадров поддерживает пользовательские маркеры и группы событий. Они отображаются в сводной таблице и в таблице подробных сведений.  
  
 Для создания маркеров и групп можно использовать API ID3DUserDefinedAnnotation или устаревшие API семейства D3DPERF_. При использовании семейства API D3DPERF_ каждому маркеру и группе можно назначить цвет. Полоса этого цвета будет отображаться в окне анализа кадров в строке, содержащей соответствующий маркер события или группу событий. Это позволяет быстро определять важные события или группы событий отрисовки.  
  
### <a name="warnings-and-errors"></a>Предупреждения и ошибки  
 Иногда анализ кадров завершается с предупреждениями или ошибками, сводка по которым приводится над временной шкалой, а подробная информация — в нижней части вкладки анализа кадров.  
  
 Как правило, предупреждения и ошибки служат только для информации и не требуют вмешательства.  
  
 Предупреждения обычно указывают на отсутствие аппаратной поддержки, но наличие обходного пути, невозможность собрать данные аппаратных счетчиков или возможную недостоверность некоторых данных производительности, например вследствие применения обходного пути.  
  
 Ошибки обычно указывают на наличие ошибок в реализации анализа кадров, ошибки в драйвере, отсутствие аппаратной поддержки и обходного пути или попытку приложения выполнить операцию, которая не поддерживается при воспроизведении.  
  
### <a name="retries"></a>Повторные попытки  
 Если во время анализа кадров в GPU происходит смена состояний питания, затронутый проход анализа необходимо выполнить повторно, так как тактовая частота GPU изменилась и относительные результаты измерения времени стали недействительны.  
  
 Число повторных попыток анализа кадров ограничено 10 попытками. Если в вашей платформе используется агрессивная модель управления питанием или технология Clock gating, это может привести к сбою анализа кадров и получению ошибки из-за превышения числа повторных попыток. Эту проблему можно устранить, уменьшив тактовую частоту и изменив модель управления электропитанием на менее агрессивную, если платформа допускает это.  
  
##  <a name="HardwareSupport"></a> Поддержка оборудования  
  
### <a name="timestamps-and-occlusion-queries"></a>Метки времени и запросы перекрытия  
 Метки времени поддерживаются на всех платформах, которые поддерживают анализ кадров. Запросы перекрытия глубины, необходимые для счетчика "Пикселей перекрыто", поддерживаются на платформах, которые поддерживают функциональный уровень 9.2 или более высокий.  
  
> [!NOTE]
>  Хотя метки времени поддерживаются на всех платформах, которые поддерживают анализ кадров, их точность и согласованность меняется от платформы к платформе.  
  
### <a name="gpu-counters"></a>Счетчики GPU  
 Поддержка аппаратных счетчиков GPU зависит от оборудования.  
  
 Так как ни одно из устройств GPU, в настоящее время предлагаемых компаниями Intel, AMD или nVidia для компьютеров, не обеспечивает надежной поддержки аппаратных счетчиков GPU, при анализе кадров данные этих счетчиков не собираются. Однако анализ кадров собираются данные аппаратных счетчиков следующие GPU, который надежно их поддерживает:  
  
- nVidia T40 (Tegra4)
  
  На всех остальных платформах, поддерживающих анализ кадров, сбор данных аппаратных счетчиков GPU не производится.  
  
> [!NOTE]
>  Так как аппаратные счетчики GPU являются аппаратными ресурсами, для сбора полного набора их показателей для каждого варианта отрисовки требуется несколько проходов. Поэтому порядок сбора показателей счетчиков GPU не определен.  
  
## <a name="unsupported-scenarios"></a>Неподдерживаемые сценарии  
 Некоторые способы использования анализа кадров не поддерживаются или просто не рекомендуются.  
  
### <a name="playback-of-high-feature-level-captures-on-down-level-devices"></a>Воспроизведение захватов высокого функционального уровня на устройствах более низкого уровня  
 При воспроизведении в анализаторе графики файла журнала графики, использующего более высокий функциональный уровень, чем тот, который поддерживается компьютером воспроизведения, происходит автоматическое переключение на WARP. При анализе кадров явное переключение на WARP не происходит и возникает ошибка, так как WARP полезен для проверки правильности приложения Direct3D, но не для анализа его производительности.  
  
> [!NOTE]
>  Хотя необходимо учитывать проблемы, связанные с функциональным уровнем, захватывать и воспроизводить файлы журнала графики можно на разных устройствах и в разных конфигурациях оборудования. Журнал графики можно воспроизвести, если файл журнала не содержит API и использует функциональные уровни, которые не поддерживаются на компьютере воспроизведения.  
  
### <a name="direct3d-10-and-lower"></a>Direct3D 10 и более ранних версий  
 Если приложение вызывает API Direct3D 10, инструменту анализа кадров не удастся распознать или профилировать его несмотря на то, что он распознается и используется другими инструментами анализатора графики.
  
> [!NOTE]
>  Это относится только к вызовам API Direct3D, но не к функциональным уровням.

### <a name="warp"></a>WARP  
 Анализ кадров предназначен для сбора данных и оптимизации производительности отрисовки на реальном оборудовании. Запуск анализа кадров на устройствах WARP возможен, но не обычно стоят достижения поскольку ПРОСТОГО ЦП выполняется медленнее, чем даже наименее-современных графических процессоров, а производительность WARP может сильно различаться в зависимости от конкретного ЦП он выполняется.  
  
##  <a name="Variants"></a> Варианты  
 Каждое изменение, которое анализ кадров вносит в способ отрисовки кадра во время воспроизведения он называется *variant*. Варианты, проверяемые при анализе кадров, соответствуют типичным, сравнительно простым изменениям, которые можно внести, чтобы повысить производительность отрисовки или качество изображения в приложении. Это, например, уменьшение размера текстур, использование сжатия текстур или включение различных типов сглаживания. Варианты переопределяют стандартный контекст и параметры отрисовки приложения. Ниже приведена сводная информация о вариантах.  
  
|Вариант|Описание|  
|-------------|-----------------|  
|**Размер окна просмотра 1 x 1**|Размеры окна просмотра для всех целевых объектов отрисовки уменьшаются до 1 x 1 пикселей.<br /><br /> Дополнительные сведения см. в разделе [вариант размера окна просмотра 1 x 1](1x1-viewport-size-variant.md)|  
|**0 x MSAA**|Многовыборочное сглаживание (MSAA) отключается для всех целевых объектов отрисовки.<br /><br /> Дополнительные сведения см. в разделе [0 x / 2 x / 4 x MSAA варианты](0x-2x-4x-msaa-variants.md)|  
|**2x MSAA**|Двукратное многовыборочное сглаживание (MSAA) включается для всех целевых объектов отрисовки.<br /><br /> Дополнительные сведения см. в разделе [0 x / 2 x / 4 x MSAA варианты](0x-2x-4x-msaa-variants.md)|  
|**4x MSAA**|Четырехкратное многовыборочное сглаживание (MSAA) включается для всех целевых объектов отрисовки.<br /><br /> Дополнительные сведения см. в разделе [0 x / 2 x / 4 x MSAA варианты](0x-2x-4x-msaa-variants.md)|  
|**Точечная фильтрация текстур**|Для всех соответствующих образцов текстур устанавливается режим фильтрации `DXD11_FILTER_MIN_MAG_MIP_POINT` (точечная фильтрация текстур).<br /><br /> Дополнительные сведения см. в разделе [точки, билинейной, Трилинейной и текстуры анизотропной фильтрации](point-bilinear-trilinear-and-anisotropic-texture-filtering-variants.md).|  
|**Билинейная фильтрация текстур**|Для всех соответствующих образцов текстур устанавливается режим фильтрации `DXD11_FILTER_MIN_MAG_LINEAR_MIP_POINT` (билинейная фильтрация текстур).<br /><br /> Дополнительные сведения см. в разделе [точки, билинейной, Трилинейной и текстуры анизотропной фильтрации](point-bilinear-trilinear-and-anisotropic-texture-filtering-variants.md).|  
|**Трилинейная фильтрация текстур**|Для всех соответствующих образцов текстур устанавливается режим фильтрации `DXD11_FILTER_MIN_MAG_MIP_LINEAR` (трилинейная фильтрация текстур).<br /><br /> Дополнительные сведения см. в разделе [точки, билинейной, Трилинейной и текстуры анизотропной фильтрации](point-bilinear-trilinear-and-anisotropic-texture-filtering-variants.md).|  
|**Анизотропная фильтрация текстур**|Задает режим фильтрации `DXD11_FILTER_ANISOTROPIC` и `MaxAnisotropy` для `16` (16-кратная анизотропная фильтрация текстур) для всех соответствующих образцов текстур.<br /><br /> Дополнительные сведения см. в разделе [точки, билинейной, Трилинейной и текстуры анизотропной фильтрации](point-bilinear-trilinear-and-anisotropic-texture-filtering-variants.md).|  
|**Формат целевого объекта отрисовки глубиной цвета 16 бит**|Для всех целевых объектов отрисовки и буферов фона задается формат пикселей `DXGI_FORMAT_B5G6R5_UNORM` (глубина цвета 16 бит, формат 565).<br /><br /> Дополнительные сведения см. в разделе [глубиной цвета 16 бит отрисовки вариант формата](16bpp-render-target-format-variant.md)|  
|**Создание MIP-карт**|MIP-карты включаются для всех текстур, не являющихся целевыми объектами отрисовки.<br /><br /> Дополнительные сведения см. в разделе [вариант создания Mip карты](mip-map-generation-variant.md).|  
|**Половинные размеры текстур**|Размеры всех текстур, не являющихся целевыми объектами отрисовки, уменьшаются вдвое по сравнению с исходными. Например, текстура размером 256 x 128 уменьшается до 128 x 64 текселя.<br /><br /> Дополнительные сведения см. в разделе [вариант текстуры половина/четверть](half-quarter-texture-dimensions-variant.md).|  
|**Четвертные размеры текстур**|Размеры всех текстур, не являющихся целевыми объектами отрисовки, уменьшаются в четыре раза по сравнению с исходными. Например, текстура размером 256 x 128 уменьшается до 64 x 32 текселя.<br /><br /> Дополнительные сведения см. в разделе [вариант текстуры половина/четверть](half-quarter-texture-dimensions-variant.md).|  
|**Сжатие текстур BC**|Включает блочное сжатие всех текстур, которые имеют вариант формата пикселей B8G8R8X8, B8G8R8A8 или R8G8B8A8. Варианты формата B8G8R8X8 сжимаются с помощью BC1; варианты форматов B8G8R8A8 и R8G8B8A8 сжимаются с помощью BC3.<br /><br /> Дополнительные сведения см. в разделе [вариант сжатия текстур BC](bc-texture-compression-variant.md).|  
  
 Результаты для большинства вариантов представляют собой четкие указания: "Уменьшение размера текстур вдвое повысит производительность на 25 процентов" или "Включение варианта 2 x MSAA приведет к снижению производительности всего на 2 процента". Другие варианты могут потребовать дополнительной интерпретации. Например, если вариант, изменяющий размеры окна просмотра на 1 x 1, приводит к значительному приросту производительности, это может указывать на то, что отрисовка замедляется из-за низкой скорости заполнения. Если же производительность изменяется незначительно, это может указывать на то, что отрисовка замедляется из-за обработки вершин.