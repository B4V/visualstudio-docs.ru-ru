---
title: "Практическое руководство. Открытие представления сообщений из окна поиска | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Представление сообщений в Spy++, открытие"
  - "открытие представления сообщений в Spy++"
ms.assetid: 601a193e-432a-417b-9406-6fec9e401264
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# Практическое руководство. Открытие представления сообщений из окна поиска
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

В некоторых случаях для выбора конечного окна и открытия представления сообщений этого окна удобнее использовать диалоговое окно **Поиск окна**.  
  
### Открытие окна представления сообщений из диалогового окна "Поиск окна"  
  
1.  Расположите окна так, чтобы было видно конечное окно и окно Spy\+\+.  
  
2.  Затем в меню **Spy** выберите команду **Найти окно**.  
  
     Откроется диалоговое окно [Поиск окна](../debugger/find-window-dialog-box.md).  
  
3.  С вкладки **Окна** перетащите **инструмент поиска** на конечное окно.  При перетаскивании в диалоговом окне **Поиск окна** отображаются сведения о выбранном окне.  
  
     либо  
  
     Если известен дескриптор интересующего окна \(например, он скопирован из отладчика\), можно ввести его в текстовое поле **Дескриптор**.  
  
4.  В поле **Отобразить** выберите пункт **Сообщения**.  
  
5.  Нажмите кнопку **ОК**.  
  
     Откроется пустое окно [представления сообщений](../debugger/messages-view.md) и на панель инструментов Spy\+\+ добавится меню **Сообщения**.  
  
6.  В меню **Сообщения** выберите пункт **Параметры журнала**.  
  
     Откроется диалоговое окно [Параметры сообщения](../debugger/message-options-dialog-box.md).  
  
7.  Выберите параметры сообщений, которые необходимо отобразить.  
  
8.  Нажмите кнопку **ОК**, чтобы начать запись сообщений.  
  
     В зависимости от выбранных параметров сообщения начнут передаваться потоком в активное окно представления сообщений.  
  
9. После получения достаточного количества сообщений выберите в меню **Сообщения** команду **Остановить запись**.