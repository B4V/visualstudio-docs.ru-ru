---
title: "Отладка кода GPU | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: c7e77a5a-cb57-4b11-9187-ecc89acc8775
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Отладка кода GPU
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Можно выполнять отладку кода C\+\+, который выполняется в графическом процессоре \(GPU\).  Поддержка отладки GPU в Visual Studio включает обнаружение состояния гонки, запуск процессов и присоединение к ним, а также интеграцию с окнами отладчика.  
  
## Поддерживаемые платформы  
 Поддерживается отладка в [!INCLUDE[win7](../debugger/includes/win7_md.md)], [!INCLUDE[win8](../debugger/includes/win8_md.md)], [!INCLUDE[winsvr08_r2](../debugger/includes/winsvr08_r2_md.md)] и [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)].  Для отладки в программном эмуляторе требуется [!INCLUDE[win8](../debugger/includes/win8_md.md)] или [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)].  Для отладки на оборудовании необходимо установить драйверы для видеокарты.  Не все производители оборудования реализуют полный набор функций для отладки.  См. информацию об ограничениях в документации производителя.  
  
> [!NOTE]
>  Независимые производители оборудования, желающие реализовать поддержку отладки GPU в Visual Studio, должны создать библиотеку DLL, реализующую интерфейс VSD3DDebug для взаимодействия с драйверами производителей.  
  
## Настройка отладки GPU  
 Отладчик не может прерывать выполнение одновременно кода ЦП и кода GPU при работе одного приложения.  По умолчанию отладчик прерывает выполнение кода ЦП.  Для отладки кода GPU следует выполнить одно из указанных ниже действий.  
  
-   В списке **Тип отладки** панели инструментов **Стандартная** выберите **Только GPU**.  
  
-   Откройте контекстное меню для своего проекта в области **Обозреватель решений** и выберите **Свойства**.  В диалоговом окне **Страницы свойств** выберите **Отладка**, после чего выберите **Только GPU** в списке **Тип отладчика**.  
  
## Запуск приложений и присоединение к ним  
 Для запуска и остановки отладки GPU можно использовать команды отладки Visual Studio.  Дополнительные сведения см. в разделе [Навигация по коду с помощью отладчика](../debugger/navigating-through-code-with-the-debugger.md).  Можно также присоединить отладчик GPU к выполняющемуся процессу, но лишь при условии, что этот процесс выполняет код GPU.  Дополнительные сведения см. в разделе [Присоединение к выполняемым процессам](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
## Команды "Выполнить текущий Tile до курсора" и "Выполнить до текущей позиции"  
 При отладке кода GPU существуют два варианта выполнения кода до текущего положения курсора.  Команды для обоих вариантов доступны в контекстном меню редактора кода.  
  
1.  По команде **Выполнить до текущей позиции** приложение выполняется до достижения текущей позиции курсора, после чего выполнение приостанавливается.  Это не означает, что текущий поток будет выполнен до позиции курсора. Инициировать приостановку выполнения может любой поток, который первым достигнет текущего положения курсора.  См. раздел [Навигация по коду с помощью отладчика](../debugger/navigating-through-code-with-the-debugger.md).  
  
2.  По команде **Выполнить текущий Tile до курсора** приложение выполняется до тех пор, пока все потоки в текущем блоке потоков \(tile\) не достигнут курсора, после чего выполнение приостанавливается.  
  
## Окна отладки  
 С помощью некоторых окон отладки можно просматривать, помечать и замораживать потоки GPU.  Дополнительные сведения см. в следующих разделах:  
  
-   [Использование окна "Параллельные стеки"](../debugger/using-the-parallel-stacks-window.md)  
  
-   [Использование окна задач](../debugger/using-the-tasks-window.md)  
  
-   [Практическое руководство. Использование окна параллельных контрольных значений](../debugger/how-to-use-the-parallel-watch-window.md)  
  
-   [Отладка потоков и процессов](../debugger/debug-threads-and-processes.md) \(панель инструментов "Место отладки"\)  
  
-   [Практическое руководство. Использование окна потоков GPU](../Topic/How%20to:%20Use%20the%20GPU%20Threads%20Window.md)  
  
## Исключения синхронизации данных  
 Отладчик может распознавать несколько условий синхронизации данных во время выполнения.  При обнаружении условия отладчик переходит в состояние приостановки выполнения.  На выбор предлагаются два варианта действий: **Прервать** или **Продолжить**.  В диалоговом окне **Исключения** предусмотрены параметры, с помощью которых можно указать, должен ли отладчик распознавать эти условия и при каких из этих условий он должен прерывать выполнение.  Дополнительные сведения см. в разделе [Управление исключениями с помощью отладчика](../debugger/managing-exceptions-with-the-debugger.md).  В диалоговом окне **Параметры** также есть возможность указать, что отладчик должен игнорировать исключения, если записываемые данные не изменяют значения данных.  Дополнительные сведения см. в разделе [Страница "Общие", папка "Отладка", диалоговое окно "Параметры"](../debugger/general-debugging-options-dialog-box.md).  
  
## Устранение неполадок  
  
### Определение ускорителя  
 Точки останова в коде GPU распознаются, только если код выполняется на ускорителе [accelerator::direct3d\_ref](../Topic/accelerator::direct3d_ref%20Data%20Member.md) \(REF\).  Если ускоритель в коде не указывается, в свойствах проекта в качестве значения **Тип ускорителя отладки** будет автоматически выбран ускоритель REF.  Если ускоритель явным образом указывается непосредственно в коде, ускоритель REF во время отладки использоваться не будет и точки останова не будут распознаваться, если только поддержка отладки не предусмотрена в самом оборудовании GPU.  Выходом из этой ситуации может быть создание собственного кода, который будет использовать ускоритель REF во время отладки.  Дополнительные сведения см. в описании свойств проекта, а также в разделах [Использование объектов accelerator и accelerator\_view](/visual-cpp/parallel/amp/using-accelerator-and-accelerator-view-objects) и [Параметры проекта для конфигурации отладки C\+\+](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
### Условные точки останова  
 Условные точки останова в коде GPU поддерживаются, но не каждое выражение может быть вычислено на устройстве.  Если выражение не может быть вычислено на устройстве, оно вычисляется в отладчике.  Отладчик, вероятно, работает медленнее, чем устройство.  
  
### Ошибка: Возникла проблема конфигурации с выбранным типом акселератора отладки.  
 Эта ошибка возникает, если значения параметров проекта не соответствуют конфигурации компьютера, на котором производится отладка.  Дополнительные сведения см. в разделе [Параметры проекта для конфигурации отладки C\+\+](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
### Ошибка: На целевом компьютере не установлен драйвер отладки для выбранного типа акселератора отладки.  
 Эта ошибка происходит при отладке на удаленном ПК.  Пока не будет начато выполнение, отладчик не может определить, установлены ли драйверы на удаленном ПК.  Драйверы предоставляются производителем видеоадаптера.  
  
### Ошибка: На удаленном сайте необходимо отключить механизм обнаружения и исправления зависания во время ожидания \(TDR\).  
 При выполнении вычислений C\+\+ AMP существует вероятность превышения контрольного времени ожидания, установленного предусмотренным в Windows механизмом обнаружения и исправления зависаний \(TDR\).  При возникновении этой ошибки вычисления прекращаются и данные утрачиваются.  Дополнительные сведения см. в разделе [Обработка ошибок TDR в C\+\+ AMP](http://go.microsoft.com/fwlink/p/?LinkId=249154).  
  
## См. также  
 [Пошаговое руководство. Отладка приложения C\+\+ AMP](../Topic/Walkthrough:%20Debugging%20a%20C++%20AMP%20Application.md)   
 [Параметры проекта для конфигурации отладки C\+\+](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Запуск отладки GPU в Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=255381)