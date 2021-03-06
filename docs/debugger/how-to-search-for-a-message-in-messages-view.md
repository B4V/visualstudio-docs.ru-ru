---
title: 'Практическое: поиск сообщения в представлении сообщений | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Message Search dialog box
- Messages view
- messages, searching for
ms.assetid: 732b7ccc-54ea-41db-823b-2b96e3e4083e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f9c00eea2034651298ff62bc50741971fc0369a8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49844917"
---
# <a name="how-to-search-for-a-message-in-messages-view"></a>Практическое руководство. Поиск сообщения в представлении сообщений
Конкретное сообщение в представлении сообщений можно найти с помощью его дескриптор, тип или идентификатор сообщения в качестве критерия поиска. Одним из них — или сочетания — будет иметь допустимые условия поиска. Также можно задать исходное направление поиска. Предопределенные поля в диалоговом окне с атрибутами выбранного сообщения.  
  
### <a name="to-search-for-a-message-in-messages-view"></a>Для поиска сообщения в представлении сообщений  
  
1. Расположение окон, поэтому Spy ++ и действующая [представления сообщений](../debugger/messages-view.md) окна являются видимыми.  
  
2. Из **поиска** меню, выберите **найти сообщение**.  
  
    [Диалоговое окно "Поиск сообщений"](../debugger/message-search-dialog-box.md) открывает.  
  
3. Перетащите **инструмент поиска** на нужное окно. При перетаскивании, **поиск сообщений** диалоговое окно отображает сведения о выбранном окне.  
  
   - или  
  
     Если у вас есть дескриптор окна сообщения, для которого необходимо просмотреть, введите его в **обрабатывать** текстовое поле.  
  
   - или  
  
     Если вы знаете тип сообщения и (или) идентификатор сообщения, необходимо, выберите их из **тип** и **сообщение** раскрывающиеся меню и снимите **обрабатывать** текстовое поле.  
  
4. Очистите все поля, для которых вы не хотите указать значения.  
  
   > [!TIP]
   >  Чтобы не загромождать экран, выберите **Скрыть Spy** параметр. Этот параметр позволяет скрывать главное окно Spy ++, оставляя только **найти окно** диалоговое окно поверх других приложений. Главное окно Spy ++ восстанавливается в том случае, если щелкнуть **ОК** или **отменить**, или при удалении **Скрыть Spy ++** параметр.  
  
5. Выберите **вверх** или **вниз** для исходное направление поиска.  
  
6. Нажмите кнопку **ОК**.  
  
   Если обнаруживается соответствующее сообщение, он выделяется в окне представления сообщений. См. в разделе [представлением "сообщения"](../debugger/messages-view.md).