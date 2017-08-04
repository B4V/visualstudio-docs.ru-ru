---
title: "Практическое руководство. Присоединение профилировщика к службе .NET для сбора статистики приложения с помощью командной строки | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a0046c47-26c8-4bec-96a0-81da05e5104a
caps.latest.revision: 28
caps.handback.revision: 28
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Практическое руководство. Присоединение профилировщика к службе .NET для сбора статистики приложения с помощью командной строки
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

В этом разделе описано, как с помощью средств командной строки средств профилирования [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] присоединить профилировщик к службе .NET Framework и собрать статистику производительности с помощью метода выборки.  
  
> [!NOTE]
>  Функции усиленной безопасности в Windows 8 и Windows Server 2012 требуют значительных изменений в способе сбора данных профилировщиком Visual Studio на этих платформах.  Для Приложений Магазина Windows также требуются новые методы сбора.  См. раздел [Профилирование приложений для Windows 8 и Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
>   
>  Программы командной строки средств профилирования расположены в подкаталоге \\Team Tools\\Performance Tools каталога установки [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].  На 64\-разрядных компьютерах доступны 64\-разрядные и 32\-разрядные версии программ.  Для использования программ командной строки профилировщика необходимо добавить путь к этим программам в переменную среды PATH окна командной строки или указать этот путь при вызове команды.  Для получения дополнительной информации см. [Указание пути к средствам командной строки](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Добавление данных об уровневом взаимодействии в сеанс профилирования требует определенных процедур со средствами профилирования командной строки.  См. раздел [Сбор данных взаимодействия уровней](../profiling/adding-tier-interaction-data-from-the-command-line.md).  
  
 Для сбора данных о производительности, полученных от службы .NET Framework, нужно воспользоваться программой [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md), чтобы инициализировать соответствующие переменные среды.  После этого следует перезагрузить компьютер, на котором размещена эта служба, и настроить его для профилирования.  Затем профилировщик присоединяется к процессу службы.  Когда профилировщик присоединен к службе, можно приостанавливать и возобновлять сбор данных.  
  
 Чтобы завершить сеанс профилирования, необходимо отсоединить профилировщик от службы и явным образом завершить его работу.  В большинстве случаев рекомендуется удалять в конце сеанса значения переменных среды, используемые для профилирования.  
  
## Присоединение профилировщика  
  
#### Присоединение профилировщика к службе .NET Framework  
  
1.  Установите службу.  
  
2.  Откройте окно командной строки.  
  
3.  Инициализируйте переменные среды, используемые для профилирования.  Type:  
  
     **VSPerfClrEnv \/globalsampleon** \[**\/samplelineoff**\]  
  
    -   Параметр **\/globalsampleon** включает выборку.  
  
    -   **\/samplelineoff** отключает связывание собранных данных с определенными строками исходного кода.  При выборе этого параметра данные назначаются только функциям.  
  
4.  Перезагрузите компьютер.  
  
5.  Откройте окно командной строки.  
  
6.  Запустите профилировщик.  Type:  
  
     **VSPerfCmd**  [\/start](../profiling/start.md) **:sample**  [\/output](../profiling/output.md) **:** `OutputFile` \[`Options`\]  
  
    -   Параметр **\/start:sample** обеспечивает инициализацию профилировщика.  
  
    -   Параметр **\/output:**`OutputFile` является обязательным при использовании параметра **\/start**.  Параметр `OutputFile` задает имя и расположение файла с данными профилирования \(VSP\-файла\).  
  
     С параметром **\/start:sample** можно использовать любые из следующих параметров.  
  
    > [!NOTE]
    >  Обычно параметры **\/user** и **\/crosssession** являются обязательными для служб.  
  
    |Команда|Описание|  
    |-------------|--------------|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`Domain`**\\**\]`UserName`|Задает домен и имя пользователя учетной записи, которая является владельцем профилируемого процесса.  Этот параметр является обязательным только в том случае, если процесс выполняется от имени пользователя, отличного от пользователя, который выполнил вход в систему.  Имя владельца процесса отображается в столбце "Имя пользователя" на вкладке "Процессы" диспетчера задач Windows.|  
    |[\/crosssession](../profiling/crosssession.md)|Включает профилирование процессов в других сеансах.  Этот параметр является обязательным, если служба выполняется в рамках другого сеанса.  Идентификатор сеанса отображается в столбце "Код сеанса" на вкладке "Процессы" диспетчера задач Windows.  Для **\/crosssession** может быть задано сокращение **\/CS**.|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Задает счетчик производительности Windows, данные которого следует собирать в процессе профилирования.|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|Используйте только с **\/wincounter**.  Задает интервал времени \(в миллисекундах\) между событиями сбора данных счетчика производительности Windows.  Значение по умолчанию — 500 мс.|  
    |[\/events](../profiling/events-vsperfcmd.md) **:** `Config`|Задает событие трассировки событий Windows, данные которого следует собирать в процессе профилирования.  События трассировки событий Windows собираются в отдельный ETL\-файл.|  
  
7.  Если необходимо, запустите службу.  
  
8.  Присоедините профилировщик к службе.  Type:  
  
     **VSPerfCmd**  [\/attach](../profiling/attach.md) **:** {`PID`&#124;`ProcName`} \[`Sample Event`\] \[[\/targetclr](../profiling/targetclr.md)**:**`Version`\]  
  
    -   Задайте идентификатор процесса \(`PID`\) или имя процесса \(ProcName\) службы.  Диспетчер задач Windows позволяет просмотреть идентификаторы и имена всех запущенных процессов.  
  
     По умолчанию данные о производительности собираются каждые 10 000 000 циклов тактовой частоты процессора без остановок.  На процессоре с частотой 1 ГГц это приблизительно 100 экземпляров в секунду.  Чтобы изменить длительность цикла тактовой частоты или задать другое событие выборки, можно воспользоваться одним из следующих параметров.  
  
    |Пример события|Описание|  
    |--------------------|--------------|  
    |[\/timer](../profiling/timer.md) **:** `Interval`|Изменяет интервал выборки на число циклов тактовой частоты без остановок, заданное параметром `Interval`.|  
    |[\/pf](../profiling/pf.md)\[**:**`Interval`\]|Изменяет событие выборки на ошибки страниц.  Если указано значение `Interval`, задает количество ошибок страниц между выборками.  По умолчанию используется значение 10.|  
    |[\/sys](../profiling/sys-vsperfcmd.md)\[`:``Interval`\]|Изменяет событие выборки на системные вызовы ядра операционной системы из процесса \(syscall\).  Если указано значение `Interval`, задает количество вызовов между выборками.  По умолчанию используется значение 10.|  
    |[\/counter](../profiling/counter.md) **:** `Config`|Изменяет событие выборки, интервал для счетчика производительности процессора и интервал, заданный параметром `Config`.|  
  
    -   **targetclr:** `Version` задает версию среды CLR для профилирования, если в приложении загружено несколько версий среды выполнения.  Необязательно.  
  
## Управление сбором данных  
 Если запущена служба, с помощью параметров средства **VSPerfCmd.exe** можно начинать и прекращать запись данных в файл данных профилировщика.  Управление сбором данных позволяет собирать данные на различных этапах выполнения программы, например, при запуске или завершении работы приложения.  
  
#### Запуск и остановка сбора данных  
  
-   Следующие пары параметров **VSPerfCmd** используются для запуска и остановки сбора данных.  Задайте каждый параметр в отдельной строке командной строки.  Запуск и приостановка сбора данных могут выполняться неоднократно.  
  
    |Команда|Описание|  
    |-------------|--------------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|Запускает \(**\/globalon**\) или останавливает \(**\/globaloff**\) сбор данных для всех процессов.|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID`  [\/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Запускает \(**\/processon**\) или останавливает \(**\/processoff**\) сбор данных для процесса с указанным идентификатором процесса \(`PID`\).|  
    |**\/attach:**{`PID`&#124;`ProcName`} [\/detach](../profiling/detach.md)\[:{`PID`&#124;`ProcName`}\]|**\/attach** запускает сбор данных для процесса, определяемого идентификатором или именем процесса.  **\/detach** останавливает сбор данных для указанного процесса или, если он не задан, для всех процессов.|  
  
## Завершение сеанса профилирования  
 Чтобы завершить сеанс профилирования, необходимо отсоединить профилировщик от всех профилируемых процессов и явным образом завершить его работу.  Для отсоединения профилировщика от приложения при использовании метода выборки можно закрыть приложение или воспользоваться параметром **VSPerfCmd \/detach**.  Затем, для завершения работы профилировщика и закрытия файла данных профилирования используется параметр **VSPerfCmd \/shutdown**.  
  
 Команда **VSPerfClrEnv \/globaloff** удаляет переменные среды, используемые для профилирования, но конфигурация системы не изменяется до перезагрузки компьютера.  
  
#### Завершение сеанса профилирования  
  
1.  Для отключения профилировщика от целевого приложения выполните одно из следующих действий.  
  
    -   Остановите службу.  
  
         – или –  
  
    -   Введите **VSPerfCmd \/detach**.  
  
2.  Завершите работу профилировщика.  Type:  
  
     **VSPerfCmd \/shutdown**  
  
3.  \(Необязательно.\) Удалите переменные среды, используемые для профилирования.  Type:  
  
     **VSPerfClrEnv \/globaloff**  
  
4.  Перезагрузите компьютер.  
  
## См. также  
 [Службы профилирования](../profiling/command-line-profiling-of-services.md)   
 [Представления данных метода выборки](../profiling/profiler-sampling-method-data-views.md)