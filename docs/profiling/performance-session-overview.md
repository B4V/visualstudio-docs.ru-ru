---
title: "Общие сведения о сеансе анализа производительности средств профилирования | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "средства профилирования, сеанс анализа производительности"
  - "сеансы анализа производительности"
ms.assetid: 35752f95-a57a-4def-b64d-cf4899669e99
caps.latest.revision: 35
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 35
---
# Общие сведения о сеансе анализа производительности средств профилирования
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

В данном обзоре приводится информация об основах профилирования.  Разработчики, у которых нет опыта анализа производительности, узнают, как средства профилирования [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] позволяют быстро повысить продуктивность их работы и производительность их кода.  Разработчики, обладающие опытом профилирования, получат представление об особенностях функций и процессов средств профилирования.  
  
 Средства профилирования [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] помогают идентифицировать проблемы производительности на уровне исходного кода, а также сравнить производительность различных возможных решений.  Мастера средств профилирования и параметры по умолчанию позволяют получить непосредственное представление о многих проблемах производительности.  Функциональные возможности и настройки средств профилирования обеспечивают полное управление процессом профилирования.  В процессе управления используются средства точной настройки разделов кода, сбор информации о времени выполнения на уровне блоков, а также включение дополнительных данных об использовании процессора и производительности системы в данные отчета.  
  
 Процесс использования средств профилирования состоит из следующих шагов.  
  
1.  Настройка сеанса анализа производительности: указание метода сбора и данных, которые необходимо собрать.  
  
2.  Сбор данных о производительности путем запуска приложения в рамках сеанса анализа производительности.  
  
3.  Анализ собранных данных для идентификации проблем с производительностью.  
  
4.  Изменение кода в интегрированной среде разработки \(IDE\) [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] для повышения производительности кода приложения.  
  
5.  Сбор данных о производительности измененного кода, сравнение данных о производительности исходного и измененного кода.  
  
6.  Создание отчета, в котором документируется повышение производительности.  
  
 Чтобы работать с информацией, предоставляемой средствами профилирования, необходимо располагать символьной информацией для профилируемых двоичных файлов, а также для двоичных файлов операционной системы Windows.  
  
## Настройка сеанса анализа производительности  
 Чтобы настроить сеанс анализа производительности, выберите метод профилирования, который будет использоваться, и данные, которые требуется собрать.  Базовые настройки можно задать при помощи диалогового окна **Мастер производительности** средства профилирования, дополнительные настройки задаются с помощью страниц свойств сеанса анализа производительности.  
  
-   Поддерживаются следующие методы сбора данных: выборка, трассировка и выделение памяти.  
  
-   В качестве значений данных могут использоваться счетчики производительности, связанные со временем, загрузкой процессора и операционной системой, а также события приложений, например сбои страниц и переходы в режим ядра.  
  
 Сеанс анализа производительности может настраиваться как этап проекта решения в рамках проекта [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], кроме того, интегрированная среда разработки [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] позволяет выполнять профилирование произвольных двоичных файлов.  Параметры сеанса могут указываться на страницах свойств сеанса анализа производительности или задаваться с помощью мастера профилирования.  
  
## Сбор данных профилирования  
 Сбор данных профилирования начинается в окне **Обозреватель производительности**.  Чтобы ограничить объем собираемых данных, можно приостанавливать и продолжать профилирование.  Кроме того, можно присоединиться к уже выполняющемуся процессу.  
  
 Как только приложение запускается, в интерфейсе IDE [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] появляется окно **Управление сбором данных**.  Окно **Управление сбором данных** позволяет выполнять профилирование отдельных составляющих приложения путем приостановки и продолжения сбора данных.  Кроме того, окно **Управление сбором данных** позволяет вставлять метки в собираемые данные.  Метки представляют собой определяемые пользователем точки данных, которые отображаются в представления профилирования и могут использоваться для фильтрации данных профилирования.  
  
 Когда работа целевого приложения завершается, средства профилирования формируют файл данных профилирования \(\*.vsp\), а в интерфейсе [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE отображается представление сводного отчета.  
  
## Анализ данных и идентификация проблем с производительностью  
 По окончании профилирования выполняется анализ данных, сводная информация отображается в окнах представления **Отчет о производительности** средств профилирования.  Сбор данных профилирования выполняется для стека вызовов и отдельных функций целевого приложения.  В представлениях отчетов отображается анализ производительности для диапазонов данных процессов, потоков, модулей, функций и строк исходного кода приложения.  В качестве данных профилирования для функции регистрируются следующие показатели.  
  
-   Общее время, затраченное на выполнение функции и дочерних функций, которые были вызваны из рассматриваемой функции \(инклюзивное время\).  
  
-   Время, затраченное только на выполнение кода самой функции \(эксклюзивное время\).  
  
 Более двенадцати различных представлений позволяют выполнять анализ данных профилирования наиболее эффективным образом.  Возможности настройки представлений пользователем позволяют выполнять фильтрацию и сортировку данных, чтобы облегчить поиск функций, которые могут вызывать проблемы с производительностью.  Функция фильтрации критического пути позволяет моментально выделить большинство активных путей в представлениях "Дерево вызовов" и "Модуль".  
  
## Изменение кода приложения  
 После идентификации одной или нескольких проблем с производительностью можно изменить код приложения с помощью интерфейса IDE [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] и собрать данные профилирования для измененного кода приложения.  
  
## Повторный сбор данных профилирования и сравнение данных, собранных в процессе двух запусков профилирования  
 В представлении "Отчет о сравнении" средств профилирования отображаются различия производительности между двумя выбранными файлами данных профилирования на уровне модулей, функций или строк исходного кода.  Можно указать значения данных профилирования, с которыми требуется выполнить сравнение; кроме того, можно переключаться между представлением сравнения и представлениями отдельных файлов.  
  
## Создание отчета о результатах  
 Строки любого отчета о производительности можно вставлять в сообщения электронной почты и электронные таблицы; кроме того, можно создавать отчеты, в которых содержатся данные из одного или нескольких представлений.  
  
## См. также  
 [Разделы общих сведений](../profiling/overviews-performance-tools.md)   
 [Пошаговое руководство. Профилирование приложений](../profiling/walkthrough-identifying-performance-problems.md)