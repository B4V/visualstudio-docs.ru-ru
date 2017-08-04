---
title: "VSPerfCLREnv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "программы командной строки, VSPerfCLREnv"
  - "командная строка, программы"
  - "средства повышения производительности, VSPerfCLREnv"
  - "средства профилирования, VSPerfCLREnv"
  - "VSPerfCLREnv - средство"
ms.assetid: 4bc9dd6e-379c-4930-9bba-59a4faa93303
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# VSPerfCLREnv
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Средство VSPerfCLREnv служит для задания переменных среды, необходимых для профилирования приложения .NET Framework.  Для этого используется следующий синтаксис.  
  
```  
VsPerfCLREnv [/option]  
```  
  
 Параметр выбирается на основе используемого метода профилирования: выборки, инструментирования или глобального.  Отдельный параметр необходим для включения данных взаимодействия уровней в данные профилирования.  Синтаксис каждого параметра описывается в следующих таблицах.  
  
> [!NOTE]
>  После завершения профилирования запустите **VSPerfCLREnv** с параметром **\/off** или **\/globaloff**, чтобы удалить переменные среды, необходимые для профилирования.  Дополнительные сведения см в разделе "Параметры средства VSPerfCLREnv для удаления переменных среды" ниже.  
  
 **Параметры VSPerfCLREnv для включения данных взаимодействия уровней**  
  
> [!WARNING]
>  Профилирование уровневого взаимодействия можно собирать с помощью [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] или [!INCLUDE[vs_pro_current_short](../profiling/includes/vs_pro_current_short_md.md)].  Однако данные профилирования уровневого взаимодействия можно просматривать только в [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] и [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)].  
  
 Профилирование взаимодействия уровней предоставляет дополнительные сведения о запросах ADO.NET в многоуровневых приложениях.  Сбор данных ведется только для синхронных вызовов функций.  Данные взаимодействия можно добавлять в любой сеанс профилирования с помощью любого из методов профилирования.  
  
 Параметры **InteractionOn** и **GlobalInteractionOn** включают сбор данных взаимодействия.  Параметр взаимодействия необходимо устанавливать после задания переменной среды VSPerfCLREnv, которая является обязательной для профилирования приложения.  
  
 В следующем примере данные взаимодействия уровней включаются в сеанс профилирования, использующий метод выборки.  
  
```  
VSPerfCLREnv /SampleOn  
VSPerfCLREnv /InteractionOn  
VSPerfCmd /Start:Sample /Output:MyApp.exe.vsp /Launch:MyApp.exe  
```  
  
 Следующий пример включает уровень взаимодействия данных в сеансе профилирования службы Windows:  
  
```  
VSPerfCLREnv /GlobalSampleOn  
VSPerfCLREnv /GlobalInteractionOn  
REM Restart the computer and start the service  
VSPerfCmd /Start:Sample /Output:MyService.exe.vsp   
VSPerfCmd /Attach:MyService.exe  
```  
  
 **Параметры средства VSPerfCLREnv для профилирования процессов с инструментированием**  
  
 В следующей таблице описаны параметры средства VSPerfCLREnv для профилирования с инструментированием.  
  
|Команда|Описание|  
|-------------|--------------|  
|**TraceOn**|Включает профилирование с помощью метода инструментирования.  Не включает профилирование выделения памяти или сбор данных о времени существования объектов.|  
|**TraceGC**|Включает профилирование выделения памяти с помощью метода инструментирования.  Не включает сбор данных о времени существования объектов.|  
|**TraceGCLife**|Включает профилирование выделения памяти и сбор данных о времени существования объектов с помощью метода инструментирования.|  
  
 **Параметры средства VSPerfCLREnv для выборочного профилирования процессов**  
  
 В следующей таблице описаны параметры средства VSPerfCLREnv для выборочного профилирования.  
  
|Команда|Описание|  
|-------------|--------------|  
|**SampleOn**|Включает профилирование с помощью метода выборки.  Не включает профилирование выделения памяти или сбор данных о времени существования объектов.|  
|**SampleGC**|Включает профилирование выделения памяти с помощью метода выборки.  Не включает сбор данных о времени существования объектов.|  
|**SampleGCLife**|Включает профилирование выделения памяти с помощью метода выборки.  Также включает сбор данных о времени существования объектов.|  
|**SampleLineOff**|Отключает сбор данных профилирования на уровне строк кода .NET.|  
  
 **Параметры средства VSPerfCLREnv для глобального профилирования**  
  
 Чтобы выполнить профилирование управляемой службы, например веб\-приложения ASP.NET, которое запускается не пользователем, а операционной системой, используйте параметры средства VSPerfCLREnv, предназначенные для глобального профилирования.  В следующей таблице приведены глобальные версии параметров VSPerfCLREnv.  Эти параметры устанавливают соответствующие переменные среды в реестре.  
  
|Команда|Описание|  
|-------------|--------------|  
|**GlobalTraceOn**|Включает глобальное профилирование с помощью метода инструментирования.  Не включает сбор событий выделения памяти или данных о времени существования объектов.|  
|**GlobalTraceGC**|Включает глобальное профилирование выделения памяти с помощью метода инструментирования.  Не включает сбор данных о времени существования объектов.|  
|**GlobalTraceGCLife**|Включает глобальное профилирование выделения памяти с помощью метода инструментирования.  Также включает сбор данных о времени существования объектов.|  
|**GlobalSampleOn**|Включает глобальное профилирование с помощью метода выборки.  Не включает сбор событий выделения памяти или данных о времени существования объектов.|  
|**GlobalSampleGC**|Включает глобальное профилирование выделения памяти с помощью метода выборки.  Не включает сбор данных о времени существования объектов.|  
|**GlobalSampleGCLife**|Включает глобальное профилирование выделения памяти с помощью метода выборки.  Также включает сбор данных о времени существования объектов.|  
  
 **Параметры средства VSPerfCLREnv для удаления переменных среды**  
  
 После завершения профилирования управляемого приложения можно использовать один из следующих параметров для удаления переменных среды, которые были добавлены средством VSPerfCLREnv.  В следующей таблице представлены параметры удаления обычных и глобальных переменных среды.  
  
|Команда|Описание|  
|-------------|--------------|  
|**Off**|Удаляет переменные среды для обычного профилирования .NET.  Этот параметр необходимо использовать, если для задания переменных среды профилировщика используются неглобальные параметры VSPerfClrEnv.|  
|**GlobalOff**|Удаляет переменные среды для глобального профилирования .NET.  Этот параметр следует использовать, если приложение запускается не профилировщиком, а операционной системой.|  
  
## Заметки  
 Если приложение запускается с помощью обозревателя производительности интегрированной среды разработки, эти параметры не требуются для профилирования управляемых приложений.  Обозреватель производительности устанавливает все необходимые параметры среды автоматически.  
  
 Если при профилировании не была задана правильная среда, то во время анализа выводится предупреждение, а все имена управляемых функций будут разрешаться неверно.  
  
## См. также  
 [Профилирование из командной строки](../profiling/using-the-profiling-tools-from-the-command-line.md)