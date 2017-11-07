---
title: "Не удается подключиться к Microsoft Visual Studio монитора удаленной отладки | Документы Microsoft"
ms.custom: 
ms.date: 08/24/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.error.remote_debug
- vs.debug.error.firewall.remotemachine
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: a1d959fc-3817-491c-831b-e6b768a3877a
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 1d4298d60886d8fe8b402b59b1838a4171532ab1
ms.openlocfilehash: 454e6919c2f2bcd56153eb222fbf59b1ddc1080e
ms.contentlocale: ru-ru
ms.lasthandoff: 09/26/2017

---
# <a name="unable-to-connect-to-the-microsoft-visual-studio-remote-debugging-monitor"></a>Unable to Connect to the Microsoft Visual Studio Remote Debugging Monitor
Это сообщение может возникать, если монитор удаленной отладки не настроен должным образом на удаленном компьютере или удаленный компьютер недоступен из-за проблем с сетью или наличия межсетевого экрана.
  
> [!IMPORTANT]
>  Если вы считаете, что получили это сообщение из-за ошибки продукта, обратитесь за помощью [сообщите об этой проблеме](../ide/how-to-report-a-problem-with-visual-studio-2017.md) в Visual Studio. Если вам нужна дополнительная помощь, обратитесь к разделу [Talk to Us](../ide/talk-to-us.md) , чтобы узнать, как связаться с корпорацией Майкрософт.

## <a name="specificerrors"></a>Что такое сообщение об ошибке?

`Unable to Connect to the Microsoft Visual Studio Remote Debugging Monitor` Сообщения является универсальным. Как правило более конкретное сообщение включается в строку ошибки и, могут помочь определить причину проблемы или поиска для более точного исправления. Вот несколько наиболее распространенных сообщений об ошибках, добавляется к главной сообщение:

- [Отладчику не удается подключиться к удаленному компьютеру. Отладчику не удалось разрешить указанное имя компьютера](#cannot_connect)
- [Запрос на подключение был отклонен удаленного отладчика](#rejected)
- [Недопустимый доступ к памяти](#invalid_access)
- [Нет ни одного сервера с указанным именем, запущенного на удаленном компьютере](#no_server)
- [Указанное имя является допустимым, но данные запрошенного типа не найден](#valid_name)
- [Удаленный отладчик Visual Studio на целевом компьютере не удается подключиться к этому компьютеру](#cant_connect_back)
- [Отказано в доступе](#access_denied)
- [Безопасность ошибка в пакете](#security_package)

## <a name="cannot_connect"></a>Отладчику не удается подключиться к удаленному компьютеру. Отладчику не удалось разрешить указанное имя компьютера

Попробуйте выполнить следующие действия:

1. Убедитесь, что введите допустимое имя компьютера и номер порта в **присоединиться к процессу** диалоговое окно или в свойствах проекта (для задания свойств в разделе [эти действия](#server_incorrect)). Имя компьютера, должно иметь следующий формат:

    `computername:port`

    > [!NOTE]
    > Номер порта должен соответствовать [номер_порта удаленного отладчика](../debugger/remote-debugger-port-assignments.md), который *должен работать под управлением* на конечном компьютере.

2. Если имя компьютера не работает, попробуйте IP-адрес и номер порта.

3. Убедитесь в том, что версия удаленного отладчика на целевом компьютере соответствует вашей версии Visual Studio. Чтобы получить правильную версию удаленного отладчика, в разделе [удаленной отладки](../debugger/remote-debugging.md).

    > [!TIP]
    > Если для присоединения к процессу и успешного подключения, но не вижу процесс, который требуется, установите **Показать процессы всех пользователей флажок**. Это будет отображать процессы, если вы подключены в учетной записи другого пользователя.

4. Если эти шаги не устранить эту ошибку, см. раздел [удаленный компьютер недоступен](#dns).

## <a name="rejected"></a>Запрос на подключение был отклонен удаленного отладчика

В **присоединиться к процессу** диалогового окна поле или в свойствах проекта, убедитесь, что имя удаленного компьютера и номер порта совпадает имя и номер порта отображаются в окне удаленного отладчика. Если неправильными, исправьте и повторите попытку.

Если эти значения верны, а в сообщении упоминаются **проверки подлинности Windows** режима, убедитесь, что удаленный отладчик находится в режиме проверку подлинности пользователя (**Сервис > Параметры**).

## <a name="invalid_access"></a>Недопустимый доступ к памяти

Произошла внутренняя ошибка. Перезапустите Visual Studio и повторите попытку.

## <a name="no_server"></a>Нет ни одного сервера с указанным именем, запущенного на удаленном компьютере

Visual Studio не удалось подключиться к удаленному отладчику. Это сообщение может возникать по нескольким причинам:

- Удаленный отладчик может выполняться под другой учетной записью. В разделе [следующие действия](#user_accounts)

- Порт заблокирован на брандмауэре. Убедитесь, что брандмауэр [не блокирует запрос](#firewall), особенно в том случае, если вы используете брандмауэр сторонних разработчиков.

- Версия удаленного отладчика не соответствует Visual Studio. Чтобы получить правильную версию удаленного отладчика, в разделе [удаленной отладки](../debugger/remote-debugging.md)


## <a name="#valid_name"></a>Указанное имя является допустимым, но данные запрошенного типа не найден

Существует на удаленном компьютере, но Visual Studio не удалось подключиться к удаленному отладчику. Это сообщение может возникать по нескольким причинам:

- Проблема DNS препятствует подключению. В разделе [эти действия](#dns).

- Удаленный отладчик может выполняться под другой учетной записью. Выполните [эти действия](#user_accounts).

- Порт заблокирован на брандмауэре. Убедитесь, что брандмауэр [не блокирует запрос](#firewall), особенно в том случае, если вы используете брандмауэр сторонних разработчиков.

- Версия удаленного отладчика не соответствует Visual Studio. Чтобы получить правильную версию удаленного отладчика, в разделе [удаленной отладки](../debugger/remote-debugging.md).

## <a name="cant_connect_back"></a>Удаленный отладчик Visual Studio на целевом компьютере не удается подключиться к этому компьютеру

Удаленный отладчик может выполняться под другой учетной записью. Удаленный отладчик, откройте **Сервис > разрешения** Добавление пользователя разрешений удаленного отладчика. Дополнительные сведения см. в разделе [удаленный отладчик выполняется под другой учетной записью](#user_accounts).

Если сообщение об ошибке также говорится о брандмауэром, брандмауэр на локальном компьютере возможно взаимодействие с удаленного компьютера, вернитесь в Visual Studio. В разделе [эти действия](#firewall).

## <a name="access_denied"></a>Отказано в доступе

Эта ошибка может отображаться, если предпринята попытка отладки на удаленном компьютере x 64 с 32-разрядного компьютера (не поддерживается).

## <a name="security_package"></a>Безопасность ошибка в пакете

Это может быть устаревший проблемы, связанные с Windows XP и Windows 7. Это статье [сведения](https://stackoverflow.com/questions/4786016/unable-to-connect-to-the-microsoft-remote-debugging-monitor-a-security-package). 

## <a name="causes-and-recommendations"></a>Причины и рекомендации

### <a name="dns"></a>Удаленный компьютер недоступен 

Если не удается подключиться, используя имя удаленного компьютера, попробуйте вместо этого использовать IP-адрес. Можно использовать `ipconfig` в командной строке на удаленном компьютере, чтобы получить адрес IPv4. Если вы используете файл HOSTS, проверьте, правильно ли настроен.

Если это не удается, убедитесь, что удаленный компьютер доступен в сети ([ping](https://technet.microsoft.com/en-us/library/cc732509(v=ws.10).aspx) удаленный компьютер). Удаленная отладка через Интернет не поддерживается, только в некоторых сценариях Microsoft Azure.
  
### <a name="server_incorrect"></a>Указано неверное имя сервера или стороннее программное обеспечение мешает работе удаленного отладчика

В Visual Studio просмотрите свойства проекта и убедитесь, что имя сервера указано правильно. В следующих разделах для [C# и Visual Basic](../debugger/remote-debugging-csharp.md#remote_csharp) и [C++](../debugger/remote-debugging-cpp.md#remote_cplusplus). ASP.NET, откройте **свойства / Web / серверов** или **свойства / Debug** в зависимости от типа проекта.

> [!NOTE]
> Для присоединения к процессу, не используются параметры удаленного в свойствах проекта.

Если имя сервера указано правильно, антивирусная программа или брандмауэр сторонних разработчиков может блокировать удаленный отладчик. При локальной отладке, это может произойти, так как Visual Studio является 32-разрядным приложением, поэтому используется 64-разрядной версии удаленного отладчика для отладки 64-разрядных приложений. 32-разрядных и 64-разрядные процессы обмениваться данными по локальной сети на локальном компьютере. Сетевой трафик не отправляется с компьютера, но приложение для обеспечения безопасности от сторонних разработчиков может блокировать обмен данными.

### <a name="user_accounts"></a>Удаленный отладчик запущен под учетной записью другого пользователя 

Удаленный отладчик будет по умолчанию принимать подключения только от пользователя, выполнившего запуск удаленного отладчика и члены группы «Администраторы». Дополнительные пользователи должны быть явно предоставлены разрешения. 
 
Решить эту проблему можно одним из указанных ниже способов.  

-   Добавить разрешения удаленного отладчика Visual Studio пользователя (в окне удаленного отладчика, выберите **Сервис > разрешения**).

-   На удаленном компьютере перезапустите удаленного отладчика под учетной записью пользователя и пароль, который используется на компьютере с Visual Studio.

    > [!NOTE]
    > Если вы используете удаленный отладчик на удаленном сервере, щелкните правой кнопкой мыши приложение удаленного отладчика и выберите команду **Запуск от имени администратора** (или запуска удаленного отладчика в качестве службы). Если вы не используете его на удаленном сервере, запустите его обычным образом.
  
-   Удаленный отладчик можно запустить из командной строки с **/ allow \<имя пользователя >** параметр: `msvsmon /allow <username@computer>`. 
  
-   Кроме того можно разрешить любому пользователю выполнять удаленную отладку. В окне удаленного отладчика, перейдите к **Сервис > Параметры** диалогового окна. Если выбрать   **Без аутентификации**, то затем можно установить флажок **Разрешить отладку любому пользователю**. Тем не менее вначале следует проверить этот параметр только в том случае, если другие варианты не сработают или если вы находитесь в частной сети.

### <a name="firewall"></a>Брандмауэр на удаленном компьютере запрещает входящие подключения к удаленному отладчику  
 Брандмауэры на компьютере Visual Studio и на удаленном компьютере нужно настроить так, чтобы разрешить обмен данными между Visual Studio и удаленным отладчиком. Информацию о портах, используемых удаленным отладчиком, см. в разделе [Remote Debugger Port Assignments](../debugger/remote-debugger-port-assignments.md). Информацию о настройке брандмауэра Windows см. в разделе [Configure the Windows Firewall for Remote Debugging](../debugger/configure-the-windows-firewall-for-remote-debugging.md).
  
### <a name="the-version-of-the-remote-debugger-doesnt-match-the-version-of-visual-studio"></a>Версия удаленного отладчика не соответствует версии Visual Studio  
 Запущенная локально версия Visual Studio должна совпадать с версией монитора удаленной отладки, запущенного на удаленном компьютере. Чтобы устранить эту проблему, скачайте и установите соответствующую версию монитора удаленной отладки. Чтобы получить правильную версию удаленного отладчика, в разделе [удаленной отладки](../debugger/remote-debugging.md).
  
### <a name="the-local-and-remote-machines-have-different-authentication-modes"></a>На локальном и удаленном компьютерах используются разные режимы аутентификации  
 На локальном и удаленном компьютерах должен использоваться один и тот же режим аутентификации. Чтобы устранить эту проблему, настройте на обоих компьютерах один и тот же режим аутентификации. Можно изменить режим проверки подлинности. В окне удаленного отладчика, перейдите к **Сервис > Параметры** диалоговое окно.
  
 Более подробную информацию о режимах аутентификации см. в статье [Обзор аутентификации Windows](https://technet.microsoft.com/en-us/library/hh831472.aspx).   
  
### <a name="anti-virus-software-is-blocking-the-connections"></a>Антивирусная программа блокирует подключения.  
 Антивирусная программа Windows разрешает подключения к удаленному отладчику, но некоторые антивирусные программы сторонних разработчиков могут блокировать их. Чтобы узнать, как разрешить эти подключения, см. документацию по используемой антивирусной программе.  
  
### <a name="network-security-policy-is-blocking-communication-between-the-remote-machine-and-visual-studio"></a>Политика сетевой безопасности блокирует обмен данными между удаленным компьютером и Visual Studio.  
 Проверьте, не блокирует ли политика сетевой безопасности обмен данными. Дополнительные сведения о политике сетевой безопасности Windows см. в разделе [параметров политики безопасности](/windows/device-security/security-policy-settings/security-policy-settings).  
  
### <a name="the-network-is-too-busy-to-support-remote-debugging"></a>Удаленная отладка невозможна из-за слишком высокой загрузки сети.  
 Попробуйте выполнить удаленную отладку в другое время или перепланировать работу в сети на другое время.  
  
## <a name="more-help"></a>Дополнительная справка  
 Чтобы получить справку более удаленный отладчик, откройте страницу справки удаленный отладчик (**Справка > использование** удаленного отладчика).
  
## <a name="see-also"></a>См. также  
 [Удаленная отладка](../debugger/remote-debugging.md)