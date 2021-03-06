---
title: Команда "Псевдоним" | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- tools.alias
helpviewer_keywords:
- aliases, Visual Studio commands
- commands, aliases
- Tools.Alias command
- command aliases
- alias command
ms.assetid: bdf857df-b5d5-450f-8c10-a6fd4dccc130
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f9fb6a4da0b18cf022ee388ff4a6fa5f399dc650
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49258522"
---
# <a name="alias-command"></a>Команда Alias
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Создает псевдоним для полной команды, полной команды с аргументами или для другого псевдонима.  
  
> [!TIP]
>  Если ввести `>alias` без аргументов, отображается текущий список псевдонимов и их определений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Tools.Alias [/delete] [/reset] [aliasname] [aliasstring]  
```  
  
## <a name="arguments"></a>Аргументы  
 `aliasname`  
 Необязательный. Имя нового псевдонима. Если значение для `aliasname` не указано, отображается список текущих псевдонимов и их определений.  
  
 `aliasstring`  
 Необязательный. Полное имя команды или существующий псевдоним и любые параметры, которые вы хотите создать в виде псевдонима. Если значение для `aliasstring` не указано, отображается имя и строка для заданного псевдонима.  
  
## <a name="switches"></a>Переключатели  
 /delete или /del или /d  
 Необязательный. Удаляет указанный псевдоним, убирая его из функции автозавершения.  
  
 /reset  
 Необязательный. Сбрасывает список предопределенных псевдонимов в исходные значения. То есть восстанавливает все предварительно определенные псевдонимы и удаляет все псевдонимы, определенные пользователем.  
  
## <a name="remarks"></a>Примечания  
 Так как псевдонимы представляют команды, они должны располагаться в начале командной строки.  
  
 При вводе данной команды нужно указать параметры сразу после нее, а не после псевдонимов. В противном случае параметр включается в состав строки псевдонима.  
  
 Параметр `/reset` запрашивает подтверждение перед восстановлением псевдонимов. У `/reset` нет краткой формы.  
  
## <a name="examples"></a>Примеры  
 Этот пример создает псевдоним `upper` для полной команды Edit.MakeUpperCase.  
  
```  
>Tools.Alias upper Edit.MakeUpperCase  
```  
  
 Этот пример удаляет псевдоним `upper`.  
  
```  
>Tools.alias /delete upper  
```  
  
 Этот пример отображает список всех текущих псевдонимов и их определений.  
  
```  
>Tools.Alias  
```  
  
## <a name="see-also"></a>См. также  
 [Команды Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Командное окно](../../ide/reference/command-window.md)   
 [Поле "Поиск/Команда"](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



