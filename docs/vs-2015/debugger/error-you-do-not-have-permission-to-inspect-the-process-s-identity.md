---
title: 'Ошибка: У вас нет разрешения на изучение процесса&#39;удостоверений s | Документация Майкрософт'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 6233d060-85b8-42be-ae5f-bde7e1d0f241
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b4aafd6215c868ff93108e3b170999a8d028e2df
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47561705"
---
# <a name="error-you-do-not-have-permission-to-inspect-the-process39s-identity"></a>Ошибка: У вас нет разрешения на изучение процесса&#39;s удостоверений
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [ошибка: у вас нет разрешения на изучение процесса&#39;удостоверений s](https://docs.microsoft.com/visualstudio/debugger/error-you-do-not-have-permission-to-inspect-the-process-s-identity).  
  
У вас нет разрешения на идентификацию процесса. Это может быть следствием системной конфигурации.  
  
 Отладчику не удалось идентифицировать процесс, что является необходимым для отладки. Наиболее вероятной причиной является отключение служб терминалов. По умолчанию службы терминалов включены. Выполните следующие действия, чтобы включить их снова.  
  
### <a name="to-enable-terminal-services"></a>Чтобы включить службы терминалов  
  
1.  Нажмите кнопку **запустить** и выберите **панели управления**.  
  
2.  В панели управления выберите **переключение к классическому виду**при необходимости, а затем дважды щелкните **Администрирование**.  
  
3.  В **Администрирование** окно, дважды щелкните **Управление компьютером**.  
  
4.  В окне «Управление компьютером» раскройте **служб и приложений** узла.  
  
5.  В разделе **служб и приложений**, нажмите кнопку **служб**.  
  
     В правой области окна появится список служб.  
  
6.  В **служб** списке, щелкните правой кнопкой мыши **служб терминалов** и выберите **свойства**.  
  
7.  В **свойства служб терминалов** окно, перейдите к **Общие** вкладку и задайте **тип запуска** для **вручную**.  
  
8.  Нажмите кнопку **ОК**.  
  
9. Перезагрузите компьютер.  
  
     Эта процедура не включает автоматически удаленный рабочий стол. Если необходимо включить удаленный рабочий стол на компьютере, выполните следующие дополнительные действия.  
  
### <a name="to-enable-remote-desktop"></a>Чтобы включить удаленный рабочий стол  
  
1.  Нажмите кнопку **запустить** и щелкните правой кнопкой мыши **Мой компьютер**.  
  
2.  Выберите **Свойства**.  
  
     **Системные свойства** откроется диалоговое окно.  
  
3.  Нажмите кнопку **удаленного**.  
  
4.  В разделе **удаленного рабочего стола**выберите **разрешить пользователям удаленное подключение к этому компьютеру**.  
  
5.  Нажмите кнопку **ОК**.  
  
## <a name="see-also"></a>См. также  
 [Ошибки удаленной отладки и их устранение](../debugger/remote-debugging-errors-and-troubleshooting.md)


