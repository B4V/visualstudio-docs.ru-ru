---
title: "Визуализация событий EventSource как маркеров | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3a10022a-5c37-48b1-a833-dd35902176b6
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# Визуализация событий EventSource как маркеров
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Визуализатор параллелизма может отображать события EventSource в качестве маркеров, и предоставляет возможность для настройки того, как должны отображаться эти маркеры.  Чтобы просмотреть метки EventSource, зарегистрируйте GUID поставщика трассировки событий Windows с помощью диалогового окна [Дополнительные параметры](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md).  У визуализатора параллелизма по умолчанию есть соглашения по представлению события EventSource как [Маркеры флагов](../profiling/flag-markers.md), [Маркеры диапазонов](../profiling/span-markers.md) и [Маркеры сообщений](../profiling/message-markers.md).  Можно настраивать, как отображаются события EventSource, путем добавления пользовательских полей на события.  Дополнительные сведения о маркерах см. в разделе [Маркеры визуализатора параллелизма](../profiling/concurrency-visualizer-markers.md).  Дополнительные сведения о событиях EventSource см. в разделе <xref:System.Diagnostics.Tracing>.  
  
## Визуализация событий EventSource по умолчанию  
 По умолчанию, визуализатор параллелизма использует следующие соглашения по представлению событий EventSource.  
  
### Тип маркера  
  
1.  События с [кодом](http://msdn.microsoft.com/ru-ru/d97953df-669b-4c55-b1a8-925022b339b7) win:Start или win:Stop можно рассматривать как начало или конец диапазона, соответственно.  Вложенные или перекрывающиеся диапазоны не могут быть отображены.  Пары событий, которые начинаются на одном потоке и заканчиваются на другом также не могут быть отображены.  
  
2.  Событие, чей код не win:Start и не win:Stop рассматривается как флаг маркера, если его [уровень](http://msdn.microsoft.com/ru-ru/dfa4e0a9-4d89-4f50-aef9-1dae0dc11726) \(поле EVENT\_RECORD.EVENT\_HEADER.EVENT\_DESCRIPTOR\) — win:Verbose или выше.  
  
3.  Во всех остальных случаях это событие обрабатывается как сообщение.  
  
### Важность  
 Следующая таблица определяет способ сопоставления уровня события события и важности маркера.  
  
|Уровень ETW|Важность в визуализаторе параллелизма|  
|-----------------|-------------------------------------------|  
|win:LogAlways|Обычные|  
|win:Critical|Critical|  
|win:Error|Critical|  
|win:Warning|Высокий|  
|win:Informational|Обычные|  
|win:Verbose|Низкий|  
|Выше, чем win:verbose|Низкий|  
  
### Имя ряда.  
 Имя задачи события используется для имени ряда.  Имя ряда остается пустым, если для данного события не указана задача.  
  
### Категория  
 Если уровень win:Critical или win:Error, то категория — Alert \(\-1\).  В противном случае категории устанавливается значение по умолчанию \(0\).  
  
### Текст  
 Если для события указано сообщение форматированного текста \(как для функции printf\), то она показывается в качестве описания маркера.  В противном случае описанием будет имя события и значения каждого поля полезных данных.  
  
## Настройка визуализации событий EventSource  
 Можно настраивать параметры отображения событий EventSource, добавив соответствующие поля к событию, как описано в следующих разделах.  
  
### Тип маркера  
 Используйте поле `cvType`, типа byte, для отслеживания типа маркера, который используется для представления события.  Ниже приведены доступные значения для cvType:  
  
|Значение cvType|Результирующий тип маркера|  
|---------------------|--------------------------------|  
|0|Сообщение|  
|1|Начало диапазона|  
|2|Конец диапазона|  
|3|Flag|  
|Все остальные значения|Сообщение|  
  
### Важность  
 Можно использовать поле `cvImportance`, типа byte, чтобы отслеживать важность параметров для события EventSource.  Однако рекомендуется контролировать отображаемую важность события с помощью использования его уровня.  
  
|Значение cvImportance|Важность в визуализаторе параллелизма|  
|---------------------------|-------------------------------------------|  
|0|Обычные|  
|1|Critical|  
|2|Высокий|  
|3|Высокий|  
|4|Обычные|  
|5|Низкий|  
|Все остальные значения|Низкий|  
  
### Имя ряда.  
 Используйте поле события `cvSeries`, строковое значение, чтобы отслеживать имя ряда, которое визуализатор параллелизма назначает событию EventSource.  
  
### Категория  
 Используйте поле `cvCategory` типа byte, чтобы отслеживать категорию, которую визуализатор параллелизма назначает событию EventSource.  
  
### Текст  
 Используйте поле `cvTextW` типа string, чтобы отслеживать описание, которое визуализатор параллелизма назначает событию EventSource.  
  
### SpanID  
 Используйте поле cvSpanId типа int, чтобы сопоставлять пары событий.  Значение для каждой пары событий start\/stop представляют cобой диапазон, который должен быть уникальным.  Обычно для параллельного кода это требует использования примитивов синхронизации, таких как <xref:System.Threading.Interlocked.Exchange%2A>, для того, чтобы убедиться, что ключ \(значение, который используется для CvSpanID\) верен.  
  
> [!NOTE]
>  На поддерживается использование SpanID для вложенных диапазонов, а именно позволения им частично перекрываться в одном и том же потоке или начинаться в одном потоке, а завершаться в другом.  
  
## См. также  
 [Маркеры визуализатора параллелизма](../profiling/concurrency-visualizer-markers.md)