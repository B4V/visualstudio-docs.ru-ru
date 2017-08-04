---
title: "Практическое руководство. Включение и выключение режима &quot;Изменить и продолжить&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
helpviewer_keywords: 
  - "/INCREMENTAL - параметр компоновщика"
  - "Применить изменения кода - команда"
  - "режим приостановки, применения изменений кода"
  - "изменения кода, сохранение изменений в режиме приостановки выполнения"
  - "Изменить и продолжить, применения изменений кода"
  - "Изменить и продолжить, отключение"
  - "Изменить и продолжить, включение"
  - "Перейти - команда"
  - "INCREMENTAL - параметр компоновщика"
  - "Шаг - команда"
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Практическое руководство. Включение и выключение режима &quot;Изменить и продолжить&quot;
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Операцию "Изменить и продолжить" можно запретить или разрешить во время разработки в диалоговом окне **Параметры**.  Этот параметр невозможно изменить в процессе отладки.  
  
 Операция "Изменить и продолжить" работает только в отладочных сборках.  В случае машинного кода C\+\+ для операции "Изменить и продолжить" требуется использовать параметр \/INCREMENTAL.  
  
## Процедуры  
  
#### Чтобы включить или отключить режим "Изменить и продолжить"  
  
1.  В меню **Сервис** выберите пункт **Параметры**.  
  
2.  В диалоговом окне **Параметры** откройте узел **Отладка** и выберите категорию **Изменить и продолжить**.  
  
3.  Чтобы включить, установите флажок **Разрешить операцию "Изменить и продолжить"**.  Чтобы отключить, снимите флажок.  
  
    > [!NOTE]
    >  Если включено средство IntelliTrace и собираются как события IntelliTrace, так и сведения о вызовах, операция "Изменить и продолжить" становится недоступна.  Дополнительные сведения см. в разделе [Настройка IntelliTrace для сбора данных об отладке](http://msdn.microsoft.com/ru-ru/7657ecab-e07e-4b1b-872d-f05d966be37e).  
  
4.  Нажмите кнопку **ОК**.  
  
## См. также  
 [Изменить и продолжить](../debugger/edit-and-continue.md)   
 [Страница "Изменить и продолжить", папка "Отладка", диалоговое окно "Параметры"](../Topic/Edit%20and%20Continue,%20Debugging,%20Options%20Dialog%20Box.md)