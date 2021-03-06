---
title: Развертывание с помощью веб-развертывания
description: Развертывание приложения с помощью веб-развертывания в Visual Studio
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 4ef232e64f308699c73c60cbe5b155f1d4ebb725
ms.sourcegitcommit: 1c675dae7c348defb32d9f7ccf7079a1062a1c4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48244127"
---
Если вы установили веб-развертывания с помощью установщика веб-платформы, можно развернуть приложение непосредственно из Visual Studio.

1. Запустите Visual Studio с правами администратора и повторно откройте проект.

    Чтобы развернуть приложение с помощью веб-развертывания, необходимы права администратора.

1. В **обозревателе решений**щелкните правой кнопкой мыши узел проекта и выберите пункт **Опубликовать**.

    Если ранее вы настроили все профили публикации **публикации** откроется панель. Нажмите кнопку **новый профиль**.

1. Для **выберите цель публикации**выберите **IIS, FTP, и т.д.** и нажмите кнопку **публикации**.

    ![RemoteDBG_Publish_IISl](../../debugger/media/remotedbg_iis_profile.png "RemoteDBG_Publish_IIS")

1. Введите параметры конфигурации исправление для настройки IIS.

    ![RemoteDBG_Publish_WebDeployl](../../debugger/media/remotedbg_iis_webdeploy_config.png "RemoteDBG_Publish_WebDeploy")

    Если имя узла не разрешается при попытке проверить в обсуждение следующих этапов **Server** текстовое поле, попробуйте IP-адрес. Включить `http://` префикс в виде **Server** поля.  Убедитесь, что используется порт 80 в **Server** текстовое поле и убедитесь, что порт 80 и порт 8172 открыты в брандмауэре.

1. Выберите **проверки**. Если проверяет установку подключения, можно попытаться опубликовать.

1. Нажмите кнопку **публикации** для публикации приложения.

    Вкладка «Вывод» показывает, если публикация выполнена успешно, и в браузере откроется.

    Если вы получите ошибку, в которых упоминаются веб-развертывания, повторно проверьте действия по установке веб-развертывания и убедитесь, что необходимые порты открыты (также веб-развертывания требуется порт 8172 необходимо открыть на сервере).

    Если приложение развертывается успешно, но не будет выполняться правильно, возможно, неполадку конфигурации IIS, ASP.NET установки или конфигурации веб-сайта. На сервере Windows откройте веб-сайт из IIS для сообщений об ошибках, а затем повторно проверьте предыдущих шагах.
