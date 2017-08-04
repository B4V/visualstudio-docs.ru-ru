---
title: "Правила производительности по идентификаторам | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a1c934c-4798-4df9-a8ef-eb17ef06b6a2
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# Правила производительности по идентификаторам
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|Предупреждение|Описание|  
|--------------------|--------------|  
|[DA0001. Использование StringBuilder для объединений](../Topic/DA0001:%20Use%20StringBuilder%20for%20concatenations.md)|Вызовы System.String.Concat составляют значительную часть данных профилирования.  Для построения строк из нескольких сегментов рекомендуется использовать <xref:System.Text.StringBuilder>.|  
|[DA0002: отсутствует файл VSPerfCorProf.dll](../profiling/da0002-vsperfcorprof-dll-is-missing.md)|Профилировщику не удалось найти VSPerfCorProf.dll во время сеанса профилирования.  Это предупреждение отображается, если программы командной строки для сбора данных профилирования используются без применения программы VSPerfCLREnv.cmd для инициализации необходимых переменных среды.|  
|[DA0003. Много выборок в режиме ядра](../profiling/da0003-many-kernel-samples.md)|Значительная часть образцов стека вызова, собранных для приложения, выполнялась в режиме ядра.  Рекомендуется воспользоваться для профилирования приложения другим методом профилирования.|  
|[DA0004: потребление значительных ресурсов процессора](../profiling/da0004-high-processor-usage.md)|Использование процессора \(ЦП\), указанное в данных профилирования, собранных с помощью метода инструментирования, было достаточно интенсивным.  При профилировании приложений, связанных с процессором, рекомендуется воспользоваться методом профилирования с выборкой.|  
|[DA0005: частые коллекции GC2](../profiling/da0005-frequent-gc2-collections.md)|В процессе сборки мусора 2\-го поколения было удалено большое число объектов памяти .NET.|  
|[DA0006. Переопределение Equals\(\) для типов значений](../profiling/da0006-override-equals-parens-for-value-types.md)|Вызовы метода Equals или операторов равенства открытого типа значения составляют значительную часть данных профилирования.  Рекомендуется внедрить более эффективный метод.|  
|[DA0007. Избегайте использования исключений для потока управления](../profiling/da0007-avoid-using-exceptions-for-control-flow.md)|В данных профилирование слишком большая частота вызова обработчиков исключений .NET Framework.  Рекомендуется использовать другую логику потока управления для сокращения числа выдаваемых исключений.|  
|[DA0008. Собрано несколько образцов](../profiling/da0008-few-samples-collected.md)|В сеансе профилирования было собрано всего несколько образцов.  Для получения более значимых результатов рекомендуется удлинить сеанс или повысить частоту выборки.|  
|[DA0009: High % time in JIT](http://msdn.microsoft.com/ru-ru/b60c1767-515c-41d9-81c2-c70d0b7024fd)|Значительная доля времени выполнения приложения была потрачена в JIT\-компиляторе.|  
|[DA0010. Затратный метод GetHashCode](../profiling/da0010-expensive-gethashcode.md)|Вызовы метода типа GetHashCode составляют значительную долю данных профилирования либо метод выделяет память.|  
|[DA0011: затратное CompareTo](../profiling/da0011-expensive-compareto.md)|Метод типа CompareTo является затратным или выделяет память.|  
|[DA0012. Слишком много вызовов метода Reflection](../Topic/DA0012:%20Significant%20amount%20of%20Reflection.md)|Вызовы методов System.Reflection, например InvokeMember и GetMember, или методов Type, например MemberInvoke, составляют значительную часть данных профилирования.  Рекомендуется по возможности заменить эти методы ранней привязкой к методам зависимых сборок.|  
|[DA0013: интенсивное использование String.Split или String.Substring](../profiling/da0013-high-usage-of-string-split-or-string-substring.md)|Вызовы методов System.String.Split или System.String.Substring составляют значительную часть данных профилирования.  Если выполняется проверка на наличие в строке подстроки, рекомендуется воспользоваться System.String.IndexOf или System.String.IndexOfAny.|  
|[DA0014: исключительно высокая скорость подкачки активной памяти на диск](../Topic/DA0014:%20Extremely%20high%20rates%20of%20paging%20active%20memory%20to%20disk.md)|Данные о производительности системы, собранные в ходе сеанса профилирования, свидетельствуют о чрезвычайно высокой скорости подкачки активной памяти на диск и с него на протяжении сеанса профилирования.  Обычно скорости подкачки на таком уровне влияют на производительность и скорость ответа приложения.  Попробуйте сократить объем выделяемой памяти, изменив алгоритмы.  Кроме того, возможно, нужно будет учесть требования к памяти приложения, снова запустив профилирование на компьютере с большим объемом памяти.|  
|[DA0017: высокая скорость подкачки активной памяти на диск](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|Данные о производительности системы, собранные в ходе сеанса профилирования, свидетельствуют о высокой скорости подкачки активной памяти на диск и с него на протяжении сеанса профилирования.  Обычно скорости подкачки на таком уровне влияют на производительность и скорость ответа приложения.  Попробуйте сократить объем выделяемой памяти, изменив алгоритмы.  Кроме того, возможно, нужно будет учесть требования к памяти приложения, снова запустив профилирование на компьютере с большим объемом памяти.|  
|[DA0018. 32\-битное приложение выполняется с ограничениями управляемой памяти процесса](../profiling/da0018-32-bit-application-running-at-process-managed-memory-limits.md)|Системные данные, собранные во время сеанса профилирования свидетельствуют о том, что кучи памяти .NET Framework близки к максимально допустимому для управляемых куч размеру в 32\-разрядном процессе.  В отчете указывается максимальное значение для куч, полученное во время активности профилируемого процесса.  Рекомендуется оптимизировать использование управляемых ресурсов приложением.|  
|[DA0021: Высокая доля сборок мусора в генерации 1](../profiling/da0021-high-rate-of-gen-1-garbage-collections.md)|Данные о производительности системы, собранные в ходе сеанса профилирования, свидетельствуют о том, что в 1\-м поколении сборки мусора было очищено значительно больше памяти, используемой для объектов .NET Framework, чем при сборе данных 0\-го поколения.|  
|[DA0022: Высокая доля сборок мусора в генерации 2](../profiling/da0022-high-rate-of-gen-2-garbage-collections.md)|Данные о производительности системы, собранные в ходе сеанса профилирования, свидетельствуют о том, что во 2\-м поколении сборки мусора было очищено значительно больше памяти, используемой для объектов .NET Framework, чем при сборке мусора 0\-го и 1\-го поколения.|  
|[DA0023. Высокое время ЦП ГК](../profiling/da0023-high-gc-cpu-time.md)|Данные о производительности системы, собранные во время профилирования, свидетельствуют о том, что количество времени, затраченное на сборку мусора, достаточно велико по сравнению с общим временем обработки данных приложения.|  
|[DA0024. Избыточное время ЦП ГК](../profiling/da0024-excessive-gc-cpu-time.md)|Данные о производительности системы, собранные во время профилирования, свидетельствуют о том, что количество времени, затраченное на сборку мусора, слишком велико по сравнению с общим временем обработки данных приложения.|  
|[DA0026: обработка чрезмерного времени ядра ЦП](../Topic/DA0026:%20Excessive%20kernel%20CPU%20time%20processing.md)|Доля времени, в течение которого ЦП работал в режиме ядра, превышает время, затраченное на пользовательский режим.  Рекомендует выполнить профилирование еще раз и сделать выборку по числу системных вызовов \(syscall\), чтобы определить причину большого времени выполнения в режиме ядра.|  
|[DA0029: неподдерживаемая версия среды CLR](../profiling/da0029-unsupported-clr-version.md)|Предпринята попытка профилирования приложения, в котором используется платформа .NET Framework версии 1.1, не поддерживаемая средствами профилирования.|  
|[DA0030: сбор измерений взаимодействия уровней для проектов баз данных](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md)|Вызовы методов <xref:System.Data> составляют значительную часть данных профилирования, но во время сеанса профилирования не были собраны данные уровневого взаимодействия.  Рекомендуется повторить профилирование и добавить данные взаимодействия.|  
|[DA0038. Большое число конфликтов при блокировке](../profiling/da0038-high-rate-of-lock-contentions.md)|Данные о производительности системы, собранные вместе с данными профилирования, свидетельствуют о достаточно большом числе конфликтов блокировки, возникающих во время выполнения приложения.  Рекомендуется повторить профилирование с использованием метода профилирования параллелизма для поиска причины конфликтов.|  
|[DA0039. Очень большое число конфликтов при блокировке](../profiling/da0039-very-high-rate-of-lock-contentions.md)|Данные о производительности системы, собранные вместе с данными профилирования, свидетельствуют о слишком большом числе конфликтов блокировки, возникающих во время выполнения приложения.  Рекомендуется повторить профилирование с использованием метода профилирования параллелизма для поиска причины конфликта.|  
|[DA0501: средняя загрузка ЦП профилируемым процессом.](../Topic/DA0501:%20Average%20CPU%20consumption%20by%20the%20Process%20being%20profiled..md)|Результатом этого измерения является процент времени, в течение которого процессор оставался занятым выполнением инструкций, поступающих из приложения.  Содержащееся в отчете значение является средним по всем интервалам измерения, в которых профилируемый процесс был активным.  На компьютерах с несколькими процессорами значение этой величины может быть больше 100%.|  
|[DA0502. Максимальное использование ЦП профилируемым процессом](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|Результатом этого измерения является максимальный процент времени, в течение которого процессор оставался занятым выполнением инструкций, поступающих из приложения.  Содержащееся в отчете значение является максимальным значением, полученным на всех интервалах измерения, в которых профилируемый процесс был активным.  На компьютерах с несколькими процессорами процент может быть больше 100%.|  
|[DA0503. Средний рабочий набор в байтах для профилируемого процесса](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|В этом сообщении указывается средний объем физической памяти в байтах, используемой процессом в данный момент \(рабочее множество\).  Рабочее множество процесса соответствует страницам из адресного пространства процесса, которые в данный момент находятся в физической памяти.|  
|[DA0505. Максимальный рабочий набор в байтах для профилируемого процесса](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|В этом сообщении указывается максимальный объем физической памяти в байтах, используемой процессом в данный момент.  Рабочее множество процесса соответствует страницам из адресного пространства процесса, которые в данный момент находятся в физической памяти.  Это правило позволяет узнать максимальное значение для рабочего множества процесса при активном профилировании.|  
|[DA0505. Среднее число байт исключительного пользования, распределенное для профилируемого процесса](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|В этом сообщении указывается средний объем виртуальной памяти, выделенной в данный момент процессом, в байтах \(байтах исключительного пользования\).  Байты исключительного пользования соответствуют участкам виртуальной памяти, которые были выделены процессом, и обращаться к которым могут только потоки, выполняющиеся внутри данного процесса.|  
|[DA0506. Максимальное число байт исключительного пользования, распределенное для профилируемого процесса](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|В этом сообщении указывается максимальный объем виртуальной памяти, выделенной в данный момент процессом, в байтах \(байтах исключительного пользования\).  Байты исключительного пользования соответствуют участкам виртуальной памяти, которые были выделены процессом, и обращаться к которым могут только потоки, выполняющиеся внутри данного процесса.|