---
title: "Запуск | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f81bde5c-3394-4b79-a315-c2f6491689b3
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# Запуск
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Параметр **Launch** запускает профилировщик с использованием метода выборки, а также запускает указанное приложение.  
  
 Для использования параметра **Launch** необходимо указать метод **Sample** в параметре **Start**.  
  
## Синтаксис  
  
```  
VSPerfCmd.exe /Launch:AppName [Options]  
```  
  
#### Параметры  
 `AppName`  
 Имя запускаемого приложения.  Поддерживаются полный и частичный пути из текущего каталога.  
  
## Допустимые параметры  
 Следующие параметры VSPerfCmd могут сочетаться с параметром **Launch** в одной командной строке.  
  
 **Start:** `Method`  
 Инициализирует сеанс профилирования командной строки и задает указанный метод профилирования.  
  
 **GlobalOn**и **GlobalOff**  
 Возобновляет \(**GlobalOn**\) или приостанавливает \(**GlobalOff**\) профилирование, но не завершает сеанс профилирования.  
  
 **ProcessOn:** `PID` и **ProcessOff**:`PID`  
 Возобновляет \(**ProcessOn**\) или приостанавливает \(**ProcessOff**\) профилирование для указанного процесса.  
  
 **TargetCLR**  
 Задает версию среды CLR .NET Framework для профилирования, если в сеансе профилирования загружено несколько версий.  По умолчанию профилируется первая загруженная версия.  
  
## Монопольные параметры  
 Следующие параметры могут использоваться только с параметром **Launch**.  
  
 **Console**  
 Запускает указанное приложение командной строки в новом окне.  
  
 **Args:** `ArgList`  
 Задает список аргументов для передачи приложению.  
  
 **LineOff**  
 Отключает сбор данных профилирования на уровне строк.  
  
## Параметры выборки  
 В командной строке **Launch** можно задать один из следующих параметров интервала выборки.  Интервал выборки по умолчанию равен 10 000 000 циклам тактовой частоты процессора.  
  
 **Timer**\[**:**`Cycles`\]**PF**\[**:**`Events`\]**Sys**\[**:**`Events`\]**Counter**\[**:**`Name`,`Reload`,`FriendlyName`\]**GC**\[:**allocation**&#124;**lifetime**\]  
 Задает числовое значение и тип интервала выборки.  
  
-   **Timer** — осуществляет выборку через каждые `Cycles` циклов тактовой частоты процессора без остановок.  Если параметр `Cycles` не задан, используется значение 10 000 000 циклов.  
  
-   **PF** \-— осуществляет выборку через каждые `Events` ошибок страниц.  Если параметр `Events` не задан, выборка осуществляется через каждые 10 ошибок страниц.  
  
-   **Sys** \-— осуществляет выборку через каждые `Events` вызовов операционной системы.  Если параметр `Events` не задан, выборка осуществляется через каждые 10 системных вызовов.  
  
-   **Counter** — осуществляет выборку через каждое значение `Reload` счетчика производительности ЦП, заданного параметром `Name`.  Кроме того, параметром `FriendlyName` можно задать строку, используемую в качестве заголовка столбца в отчетах профилировщика.  
  
-   **GC** \-— собирает данные памяти .NET.  По умолчанию \(**allocation**\) данные собираются для каждого события выделения памяти.  Если указан параметр **lifetime**, сбор данных также будет вестись для каждого события сбора мусора.  
  
## Пример  
 В этом примере демонстрируется использование параметра **Launch** для запуска приложения.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## См. также  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Профилирование автономных приложений](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Профилирование веб\-приложений ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Службы профилирования](../profiling/command-line-profiling-of-services.md)