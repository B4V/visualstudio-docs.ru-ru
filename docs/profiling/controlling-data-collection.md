---
title: "Управление сбором данных в средствах профилирования | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "расширенные задачи средств профилирования"
  - "средства профилирования, расширенные задачи"
ms.assetid: e713ad63-b948-46f3-8db9-59b30922ebe5
caps.latest.revision: 27
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 27
---
# Управление сбором данных в средствах профилирования
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Средства профилирования [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] позволяют управлять сбором данных в ходе сеанса анализа производительности и задавать профилируемые функции.  В этом разделе описывает запуск и останов сбора данных с помощью окон **Обозреватель производительности** и **Управление сбором данных**, а также выбор объектов, для которых выполняется сбор данных профилирования.  
  
## Общие задачи  
  
|Задача|Связанное содержимое|  
|------------|--------------------------|  
|**Запуск и остановка профилирования:** Вы можете начинать профилирование приложения, когда запускается приложение, или можно подключить профилировщик к уже выполняемому процессу.  Во время выполнения целевого приложения сбор данных можно приостанавливать и возобновлять.  Чтобы закончить сеанс профилирования, закройте целевое приложение или отключите профилировщик от выполняемого процесса.|-   [Практическое руководство. Начало и завершение профилирования](../profiling/how-to-start-and-end-performance-data-collection.md)<br />-   [Практическое руководство. Присоединение профилировщика к выполняющемуся процессу и его отсоединение от этого процесса](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md)<br />-   [Практическое руководство. Приостановка и возобновление профилирования](../Topic/How%20to:%20Pause%20and%20Resume%20Performance%20Data%20Collection.md)|  
|**Настройка профилирования инструментирования для ограничения собранных данных:** Вы можете использовать свойства конфигурации сеанса анализа производительности, чтобы ограничить данные, собранные в ходе запусков профилирования, которые используют метод инструментирования.  Можно включать или исключать определенные файлы .dll, пространства имен, классы и функции.  Кроме того, можно исключать функции, которые не соответствуют заданному пороговому размеру.|-   [Практическое руководство. Ограничение инструментирования указанными библиотеками DLL](../profiling/how-to-limit-instrumentation-to-specific-dlls.md)<br />-   [Практическое руководство. Ограничение инструментирования указанными функциями](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [Практическое руководство. Исключение и включение малых функций при инструментировании](../Topic/How%20to:%20Exclude%20or%20Include%20Short%20Functions%20from%20Instrumentation.md)|  
  
## Связанные разделы  
 [Настройка сеансов анализа производительности](../profiling/configuring-performance-sessions.md)  
  
## См. также  
 [Использование средств профилирования](../profiling/performance-explorer.md)