---
title: "Вкладка &quot;Общие&quot; диалогового окна &quot;Свойства потока&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "работа с потоками [Visual Studio], свойства потоков"
  - "свойства потока"
ms.assetid: 46b6c668-6786-456e-97dc-337bcac0d812
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# Вкладка &quot;Общие&quot; диалогового окна &quot;Свойства потока&quot;
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Это диалоговое окно используется для получения дополнительных сведений о конкретном потоке.  Чтобы открыть это диалоговое окно, переместите фокус на окно [Представление потоков](../debugger/threads-view.md) или откройте [Представление сообщений](../debugger/messages-view.md) и разверните сообщение.  Выберите любой узел потока в дереве, затем выберите в меню **Вид** пункт **Свойства**.  
  
 Диалоговое окно **Свойства потока** содержит одну область — вкладку **Общие**.  Доступны следующие параметры:  
  
|Entry|Описание|  
|-----------|--------------|  
|**Имя модуля**|Имя модуля.|  
|**Идентификатор потока**|Уникальный идентификатор этого потока.  Обратите внимание, что идентификаторы потоков используются неоднократно; т. е. они определяют конкретный поток только в течение времени его существования \(и могут определять другой поток после завершения существования первого\).|  
|**Идентификатор процесса**|Уникальный идентификатор этого процесса.  Номера идентификаторов процессов используются неоднократно; т. е. они определяют конкретный процесс только в течение времени его существования \(и могут определять другой процесс после завершения существования первого\).  При выполнении программы создается тип объекта процесса.  Все потоки процесса разделяют одно адресное пространство и могут обращаться к одним данным.  Выберите это значение для просмотра свойств идентификатора процесса.|  
|**Состояние потока**|Текущее состояние потока.  Выполняющийся поток использует процессор; ожидающий поток готовится к использованию процессора.  Готовый поток ожидает возможность использования процессора, поскольку он занят.  Поток в состоянии перехода ожидает выполнения ресурса, например ожидает обращения к стеку выполнения от диска.  Ожидающий поток не нуждается в процессоре, поскольку ожидает завершения внешней операции или освобождения ресурса.|  
|**Причина состояния ожидания**|Применимо только к потокам в состоянии ожидания.  Для обмена данными с защищенными подсистемами используются пары событий.|  
|**Время ЦП**|Общее время ЦП, затраченное на процесс и его потоки.  Равно сумме времени работы в пользовательском режиме и времени работы в привилегированном режиме.|  
|**Время работы в пользовательском режиме**|Общее время, затраченное потоком на выполнение кода в пользовательском режиме.  Приложения выполняются в пользовательском режиме так же, как и подсистемы, например диспетчер окон и графическое ядро.|  
|**Время работы в привилегированном режиме**|Общее время, затраченное потоком на выполнение кода в привилегированном режиме.  При вызове системной службы Windows она выполняется в привилегированном режиме, чтобы получить доступ к защищенным данным системы.  Доступ к таким данным для потоков, выполняющихся в пользовательском режиме, блокируется.  Обращения к системе могут быть явными или неявными, как, например, при ошибке страницы или прерывании.|  
|**Затраченное время**|Общее время в секундах, в течение которого выполнялся поток.|  
|**Текущий приоритет**|Текущий динамический приоритет потока.  Потоки в пределах процесса могут повышать и понижать свой базовый приоритет относительно базового приоритета самого процесса.|  
|**Базовый приоритет**|Текущий базовый приоритет потока.|  
|**Начальный адрес**|Начальный виртуальный адрес потока.|  
|**User PC**|Счетчик пользовательской программы для потока.|  
|**Контекстные переключатели**|Количество переключателей от одного потока к другому.  Переключатели потоков могут применяться как внутри единого процесса, так и для нескольких процессов.  Переключатель потока может быть активирован запросом информации от одного потока к другому или прерыванием потока с более низким приоритетом, если поток с более высоким приоритетом готов к выполнению.|