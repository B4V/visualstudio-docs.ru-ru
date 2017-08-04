---
title: "Методы отладки CRT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.runtime.debugging"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "CRT - библиотека, отладка"
  - "отладка [C++], поддержка отладки CRT"
  - "отладка [CRT]"
ms.assetid: 9be561f6-14a8-44ff-925d-d911d5b8e6ff
caps.latest.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 20
---
# Методы отладки CRT
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Эти методы могут пригодиться при отладке программы с использованием библиотеки времени выполнения языка С \(CRT\).  
  
## В этом подразделе  
 [Работа с библиотекой отладки CRT](../debugger/crt-debug-library-use.md)  
 Поддержка отладки для библиотеки CRT и инструкции по применению ее средств.  
  
 [Макросы для создания отчетов](../debugger/macros-for-reporting.md)  
 Сведения о макросах **\_RPTn** и **\_RPTFn** \(определенных в CRTDBG.H\), заменяющих оператор `printf` для отладки.  
  
 [Версии отладки функций выделения кучи](../debugger/debug-versions-of-heap-allocation-functions.md)  
 Специальные отладочные версии функций выделения кучи, содержащие сведения о том, как CRT отображает вызовы, как избежать преобразования, а также преимущества явных вызовов, отслеживание отдельных типов выделений в клиентских блоках и результаты отсутствия описания \_DEBUG.  
  
 [Сведения о куче отладки CRT](../debugger/crt-debug-heap-details.md)  
 Ссылки на управление памятью и отладочную кучу, типы блоков в отладочной куче, использование кучи, функции отчета о состоянии кучи, отслеживание запросов на выделение кучи.  
  
 [Написание функций отладочных ловушек](../debugger/debug-hook-function-writing.md)  
 Ссылки на функции\-ловушки клиентского блока, функции\-ловушки выделения, ловушки выделения и выделения памяти CRT, а также отчетные функции\-ловушки.  
  
 [Обнаружение утечек памяти с помощью библиотеки CRT](../debugger/finding-memory-leaks-using-the-crt-library.md)  
 Рассматриваются способы обнаружения и изоляции утечек памяти с помощью отладчика и библиотеки времени выполнения языка C \(CRT\).  
  
## Связанные подразделы  
 [Отладка машинного кода](../debugger/debugging-native-code.md)  
 Описание некоторых наиболее часто возникающих проблем, связанных с отладкой, и методов отладки для приложений C и C\+\+.  
  
 [Безопасность отладчика](../debugger/debugger-security.md)  
 Рекомендации по безопасной отладке.