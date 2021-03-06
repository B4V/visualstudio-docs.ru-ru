---
title: Диагностика графики в Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics
ms.assetid: fa69c550-62a7-41b5-bb1f-7eb04af1a6e8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3b8103db254e8ee7dd095f0dcd6e7890d4ab446e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49872581"
---
# <a name="visual-studio-graphics-diagnostics"></a>Диагностика графики в Visual Studio
Visual Studio*диагностики графики* — это набор средств для регистрации и последующего анализа проблем отрисовки и производительности в приложениях Direct3D. Диагностику графики можно использовать для приложений, которые выполняются локально на компьютере под управлением Windows, в эмуляторе устройства Windows либо на удаленном компьютере или устройстве.  

 Рабочий процесс диагностики графики начинается с регистрации того, как приложение использует Direct3D — в оперативном режиме непосредственно во время выполнения. Это позволяет сразу проанализировать поведение приложения, предоставить соответствующие сведения для общего доступа либо сохранить их для использования в дальнейшем. Сеансы регистрации можно инициировать и контролировать вручную из Visual Studio или с помощью средства командной строки для захвата **dxcap.exe**. Сеансы регистрации также можно инициировать и контролировать программно с помощью интерфейсов API захвата данных диагностики графики.  

 После записи сеанса записи пакета его содержимое можно воспроизвести в Visual Studio *анализатора графики* в любое время, воссоздавая записанные кадры с использованием точно таких же ресурсов и команд отрисовки приложения. Затем с помощью инструментов, предоставляемых в окне анализатора графики, любые записанные кадры можно проанализировать более подробно. С помощью этих инструментов можно проверить любой вызов Direct3D API, ресурс, объект состояния конвейера, этап конвейера или даже полный журнал всех пикселей в записанном кадре. Благодаря совместному использованию этих инструментов проблемы с отрисовкой можно анализировать интуитивно, начиная с ее проявления на записанном кадре и выполняя детализацию до первопричины в исходном коде приложения, шейдерах или графических ресурсах.  

 Для диагностики проблем производительности, захваченный кадр можно проанализировать с помощью *анализ кадров* средство. Этот инструмент анализирует потенциальные оптимизации производительности, автоматически изменяя способ использования Direct3D приложением и оценивая все отклонения. Возможно, раньше вам приходилось вручную вносить и оценивать такие изменения просто для того, чтобы подобрать нужное. Благодаря анализу кадров вы можете вносить только те изменения, вы обязательно дадут результат.  

 Диагностика графики помогает обогатить графическую составляющую приложения Direct3D и оптимизировать его выполнение.  

 По-прежнему [Обзор](overview-of-visual-studio-graphics-diagnostics.md) для получения дополнительных сведений о возможностях диагностики графики Visual Studio.  

## <a name="in-this-section"></a>В этом разделе  
 [Обзор набора средств Visual Studio для Unity](overview-of-visual-studio-graphics-diagnostics.md)  
 Содержит вводные сведения о рабочем процессе и средствах диагностики графики.  

 [Начало работы](getting-started-with-visual-studio-graphics-diagnostics.md)  
 В этом разделе вы узнаете, как установить компонент диагностики графики Visual Studio и начать использовать его для приложения Direct3D.  

 [Capturing Graphics Information](capturing-graphics-information.md)  
 Для использования диагностики графики при изучении проблемы отрисовки в приложении сначала необходимо записать информацию о том, как приложение использует DirectX. Во время сеанса записи, что и ваше приложение выполняется в обычном режиме, вы *захвата* (иными словами, выберите) кадры, которые вас интересуют. Захваченные данные содержат подробные сведения о том, как отрисовываются кадры. Собранные данные можно сохранить в виде документа журнала графики, чтобы просмотреть его позже или показать другим членам команды.  

 [Использование GPU](gpu-usage.md)  
 Чтобы использовать диагностику графики для профилирования приложения, используйте инструмент «Использование GPU». Этот инструмент можно использовать в сочетании с другими инструментами профилирования, такими как «Загрузка ЦП», для сопоставления активности ЦП и GPU, которая может вызывать появление проблем с производительностью в приложении.  

 [Документ журнала графики](graphics-log-document.md)  
 Чтобы начать исследование записанного журнала графики, используйте окно документа журнала графики для выбора захваченного кадра — или даже определенного пикселя, так что можно подробно рассмотреть *события* (т. е. вызовы API DirectX), влияют на его .  

 [Анализ кадров](graphics-frame-analysis.md)  
 После выбора кадра используйте анализ кадров графики для изучения и настройки производительности отрисовки.  

 [Список событий](graphics-event-list.md)  
 После выбора кадра используйте **список событий графики** для просмотра его событий, чтобы определить, связаны ли они с проблемой отрисовки.  

 [Состояние](graphics-state.md)  
 Окно состояния помогает понять состояние графики на момент возникновения текущего события.  

 [Этапы конвейера](graphics-pipeline-stages.md)  
 В **этапы графического конвейера** окне вам изучить, как выбранное событие обрабатывается каждым этапом графического конвейера, чтобы можно было определить, где проблема отрисовки появилась впервые. Анализ этапов конвейера особенно полезен, когда объект не отображается из-за неверного преобразования или когда один из этапов выдает результат, не соответствующий ожиданиям следующего этапа.  

 [Стек вызовов событий](graphics-event-call-stack.md)  
 Использовании **стек вызовов событий графики** для просмотра стека вызовов выбранного события таким образом, чтобы можно было обращаться к коду приложения, связанные с проблемой отрисовки.  

 [Журнал пикселей](graphics-pixel-history.md)  
 С помощью **журнал пикселей графики** окно, чтобы проанализировать, как текущий выбранный пиксель влияют события, можно определить событие или сочетание событий, которое вызывает определенные типы проблем отрисовки. Журнал пикселей особенно полезен, когда объект обрабатывается неправильно из-за того, что выходные данные пиксельного шейдера неверны или были неправильно объединены с буфером кадров, или когда объект даже не появляется, поскольку его пиксели были удалены до попадания в буфер кадров.  

 [Таблица объектов](graphics-object-table.md)  
 Использовании **таблица графических объектов** для изучения свойств и содержимого конкретных объектов Direct3D и ресурсы, которые действуют для текущего выбранного события. Таблица объектов может помочь определить контекст графического устройства, который активен во время события, и изучить содержимое графических ресурсов, например буферов констант, буферов вершин и текстур.  

 [Отладчик HLSL](hlsl-shader-debugger.md)  
 Чтобы изучить, как код шейдера для выбранного события и этапа конвейера графики ведет себя, используйте **отладчик HLSL** осуществлять пошаговое выполнение кода, проверять содержимое переменных и выполнять другие стандартные задачи отладки. Отладчик HLSL можно также использовать для проверки кода вычислительного шейдера независимо от того, обрабатываются ли его результаты далее конвейером графики или просто считываются приложением.  

 [Программа командной строки для захвата](command-line-capture-tool.md)  
 Используйте программу командной строки для быстрого захвата и воспроизведения графических данных, не прибегая к Visual Studio или программному захвату. В частности, программу командной строки можно использовать в целях автоматизации или в тестовой среде.  

 [Примеры](graphics-diagnostics-examples.md)  
 Несколько примеров, демонстрирующих использование средств диагностики графики вместе для выявления различных типов проблем отрисовки.  

## <a name="related-sections"></a>Связанные разделы  

| Заголовок | Описание |
| - | - |
| [Обзор функций отладчика](../debugging-in-visual-studio.md) | Содержит вводные сведения о функциональных возможностях отладки в [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. |
| [DirectX Graphics and Gaming](http://go.microsoft.com/fwlink/?LinkId=256498) | Содержит ссылки на статьи, посвященные технологиям графики DirectX. |

