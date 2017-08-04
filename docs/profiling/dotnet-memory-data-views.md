---
title: "Представления данных в памяти в средствах профилирования .NET | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "представления методов профилирования памяти .NET"
  - "средства профилирования, представления профилирования памяти .NET"
ms.assetid: 79184d8e-769b-4ace-be2b-521147772081
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Представления данных в памяти в средствах профилирования .NET
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

В этом разделе содержатся справочные сведения о представлениях и отчетах по файлам данных профилировщика, содержащих данные памяти .NET профилировщика.  
  
## В этом подразделе  
 [Представление "Сводка"](../profiling/summary-view-dotnet-memory-data.md)  
 Перечисляет функции и типы, которым выделяется больше всего памяти.  
  
 [Представление выделения](../profiling/dotnet-memory-allocations-view.md)  
 Перечисляет типы, выделенные в сеансе профилирования, и деревья вызовов \(пути выполнения\), полученные при выделении типа.  
  
 [Представление "Время существования объектов"](../profiling/object-lifetime-view.md)  
 Перечисляет типы, выделенные в сеансе профилирования, а также количество экземпляров, размер в байтах и сборку мусора типа.  
  
 [Представление "Дерево вызовов" — выборка](../profiling/call-tree-view-dotnet-memory-sampling-data.md)  
 Отображает иерархическое дерево, представляющее пути выполнения и данные о выделении памяти функциям в сеансе профилирования.  
  
 [Представление "Модули" — выборка](../profiling/modules-view-dotnet-memory-sampling-data.md)  
 Организует данные о выделении памяти .NET и перечисляет функции, строки исходного кода и инструкции, выполняемые при выделении памяти.  
  
 [Представление "Вызывающий\/вызываемый" —выборка](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)  
 Перечисляет данные о выделении памяти для выбранной функции, функций, вызвавших выбранную функцию, и функций, вызванных ею.  
  
 [Представление "Функции" — выборка](../profiling/functions-view-dotnet-memory-sampling-data.md)  
 Перечисляет данные о выделении памяти для функций в сеансе профилирования.  
  
 [Представление "Строки" — выборка](../profiling/lines-view-dotnet-memory-sampling-data.md)  
 Перечисляет данные о выделении памяти для строк исходного кода функций в сеансе профилирования.  
  
 [Представление указателей инструкций — выборка](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)  
 Перечисляет данные о выделении памяти для инструкций функций в сеансе профилирования.  
  
 [Представление "Дерево вызовов" — инструментирование](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)  
 Отображает иерархическое дерево, представляющее пути выполнения, данные о выделении памяти и подробные сведения о времени для инструментированных функций в сеансе профилирования.  
  
 [Представление "Модули" — инструментирование](../profiling/modules-view-dotnet-memory-instrumentation-data.md)  
 Организует данные профилирования по модулям и перечисляет функции, сведения о выделении памяти и подробные сведения о времени для модуля.  
  
 [Представление "Вызывающий\/вызываемый" — инструментирование](../profiling/caller-callee-view-net-memory-instrumentation-data.md)  
 Отображает данные о выделении памяти и подробные сведения о времени для выбранной инструментированной функции, функций, вызвавших выбранную функцию, и функций, вызванных ею.  
  
 [Представление "Функции" — инструментирование](../profiling/functions-view-dotnet-memory-instrumentation-data.md)  
 Перечисляет данные о выделении памяти для инструментированных функций в сеансе профилирования.  
  
## Ссылка  
 [Представление сведений о функции](../profiling/function-details-view.md)  
 Отображает графическую схему связей между выбранной функцией и функциями, которые вызывали выбранную функцию и вызывались ею.  
  
 [Представление "Процесс"](../profiling/process-view.md)  
 Содержит список времени начала и завершения процессов и потоков.  
  
 [Представление меток](../profiling/marks-view.md)  
 Содержит список трассировки событий Windows и событий выборки, вставленных в файл данных профилирования.  
  
## Связанные подразделы  
 [Представления данных метода выборки](../profiling/profiler-sampling-method-data-views.md)  
 Справочные сведения, касающиеся представлений и отчетов по файлам данных профилировщика, которые создаются с помощью метода выборки.  
  
 [Представление данных метода инструментирования](../profiling/instrumentation-method-data-views.md)  
 Справочные сведения по представлениям и отчетам файлов данных профилировщика, которые создаются с помощью метода инструментирования.