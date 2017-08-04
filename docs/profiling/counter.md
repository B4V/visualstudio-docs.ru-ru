---
title: "Counter | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa4b4cdb-e6ea-433a-9579-56f3785e1385
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 729b7ee61438ebd301f639518414051d57658244
ms.lasthandoff: 02/22/2017

---
# <a name="counter"></a>Счетчик
Параметр **Counter** собирает данные от счетчиков производительности для процессоров (оборудования).  
  
-   Если вы используете метод профилирования с выборкой, параметр **Counter** позволяет указать аппаратный счетчик производительности и число событий счетчика, которое будет использоваться в качестве интервала выборки. При использовании выборки можно указать только один счетчик.  
  
-   Если вы используете метод профилирования с инструментированием, количество событий счетчика, произошедших в интервале между предыдущим и текущим событиями сборки, указываются в отдельных полях отчета профилировщика. При использовании инструментирования можно указать несколько параметров **Counter**.  
  
 Каждый тип процессора использует собственный набор аппаратных счетчиков производительности. Профилировщик определяет набор стандартных счетчиков производительности, которые используются в большинстве процессоров. Чтобы получить список универсальных и специализированных счетчиков, доступных на вашем компьютере, воспользуйтесь командой VSPerfCmd **QueryCounters**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
VSPerfCmd.exe {/Launch:AppName | /Attach PID} /Counter:Name[,Reload[,FriendlyName]][Options]  
```  
  
```  
VSPerfCmd.exe /Start:Method /Counter:Name[,Reload[,FriendlyName]][/Counter:Name[,Reload[,FriendlyName]]][Options]  
```  
  
#### <a name="parameters"></a>Параметры  
 `Name`  
 Имя счетчика. Используйте параметр VSPerfCmd.exe **/QueryCounters**, чтобы получить список имен счетчиков производительности, доступных на конкретном компьютере.  
  
 `Reload`  
 Число событий счетчика в интервале выборки. Не используйте этот параметр в сочетании с методом инструментирования.  
  
 `FriendlyName`  
 (Необязательно) Строка, используемая вместо `Name` в заголовках столбцов для представлений и отчетов профилировщика.  
  
## <a name="required-options"></a>Обязательные параметры  
 Параметр Counter можно использовать только с одним из следующих параметров:  
  
 **Start:** `Trace`  
 Инициализирует профилировщик для использования метода инструментирования.  
  
 **Launch:** `AppName`  
 Запускает профилировщик вместе с указанным приложением. Профилировщик при этом должен быть инициализирован для использования метода выборки.  
  
 **Attach:** `PID`  
 Запускает профилировщик и присоединяет его к процессу, заданному идентификатором процесса. Профилировщик при этом должен быть инициализирован для использования метода выборки.  
  
## <a name="example"></a>Пример  
 В этом примере демонстрируется сбор информации о приложении с помощью метода выборки через каждые 1000 тактов универсального счетчика профилировщика NonHaltedCycles.  
  
 Пример метода инструментирования показывает, как инициализировать профилировщик для сбора событий счетчика L2InstructionFetches. Имя счетчика L2InstructionFetches зависит от конкретного процессора.  
  
```  
; Sample Method Example  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Counter:NonHaltedCycles,1000,"Non-Halted Cycles"  
  
;INSTRUMENTATION METHOD EXAMPLE  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /Counter:L2InstructionFetches,,"L2 Cache Instruction Fetches"  
```  
  
## <a name="see-also"></a>См. также  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Профилирование автономных приложений](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Профилирование веб-приложений ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Профилирование служб](../profiling/command-line-profiling-of-services.md)