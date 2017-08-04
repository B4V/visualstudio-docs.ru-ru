---
title: "Практическое руководство. Подключение к базе данных &quot;Борей&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "подключения [Visual Studio], база данных "Борей""
  - "учебная база данных Northwind"
ms.assetid: cc6cb79f-d035-41f8-b398-8d4a45922bfb
caps.latest.revision: 29
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# Практическое руководство. Подключение к базе данных &quot;Борей&quot;
По мере изучения принципов создания приложений базы данных с помощью Visual Studio вам потребуется подключиться к базе данных "Борей", чтобы проследить за множеством примеров из данного продукта, приведенных в настоящей документации.  В зависимости от того, какой пример вы рассматриваете, вы подключитесь к этой базе данных в SQL Server или в файле базы данных, например для Microsoft Access или SQL Server.  
  
## Создание подключений к данным для базы данных "Борей"  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### Создание подключения к данным для базы данных "Борей" \(SQL Server\)  
  
1.  В меню **Вид** выберите **Обозреватель серверов**\/**Обозреватель баз данных**.  
  
2.  В разделе **Обозреватель серверов**\/**Обозреватель баз данных** откройте контекстное меню элемента **Подключения данных** и выберите команду **Добавить подключение**.  
  
     После выбора элемента **Добавить подключение** отображается диалоговое окно **Выбор источника данных** или диалоговое окно **Добавить подключение**.  
  
3.  В диалоговом окне **Выбор источника данных** выберите **Microsoft SQL Server** и нажмите кнопку **ОК**.  
  
     Если отображается диалоговое окно **Добавить подключение**, а **Источник данных** отличается от **Microsoft SQL Server \(SqlClient\)**, нажмите кнопку **Изменить**, чтобы открыть диалоговое окно **Сменить источник данных**, выберите **Microsoft SQL Server** и нажмите кнопку **ОК**.  
  
4.  В списке **Имя сервера** укажите имя сервера, на котором расположена база данных "Борей".  
  
5.  В зависимости от требований вашей версии SQL Server и базы данных "Борей" выберите **Использовать аутентификацию Windows** или **Использовать аутентификацию SQL Server** и введите определенное имя пользователя и определенный пароль для входа на компьютер с запущенной системой SQL Server.  
  
6.  Выберите базу данных "Борей" в списке **Выберите или введите имя базы данных**.  
  
7.  Выберите **Проверить подключение**, чтобы проверить возможность взаимодействия с базой данных "Борей".  
  
8.  Нажмите кнопку **ОК**.  
  
     Подключение к данным для базы данных "Борей" добавляется в **Обозреватель серверов**\/**Обозреватель баз данных**.  
  
 Кроме подключения к удаленному экземпляру базы данных SQL Server, вы также можете подключиться непосредственно к тем файлам, которые содержат эту базу данных.  Это позволяет добавить файлы базы данных прямо в проект, где их можно развернуть в составе приложения.  В настоящее время поддерживаются следующие файлы локальной базы данных: файлы базы данных SQL Server Compact \(.SDF\), файлы базы данных [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] и SQL Server Express \(.MDF\) и файлы базы данных Microsoft Access \(.MDB или .ACCDB\).  
  
#### Создание подключения данных к базе данных "Борей" — файлу базы данных SQL Server \(.MDF\)  
  
1.  В меню **Вид** выберите **Обозреватель серверов**\/**Обозреватель баз данных**.  
  
2.  В разделе **Обозреватель серверов**\/**Обозреватель баз данных** откройте контекстное меню элемента **Подключения данных** и выберите команду **Добавить подключение**.  
  
     После выбора элемента **Добавить подключение** отображается диалоговое окно **Выбор источника данных** или диалоговое окно **Добавить подключение**.  
  
3.  В диалоговом окне **Выбор источника данных** выберите **Файл базы данных Microsoft SQL Server** и нажмите кнопку **ОК**.  
  
4.  При отображении диалогового окна **Добавить подключение** убедитесь, что для параметра **Источник данных** задано значение **Файл базы данных Microsoft SQL Server \(SqlClient\)**.  Если значение **Файл базы данных Microsoft SQL Server \(SqlClient\)** не задано, выберите **Изменить**, чтобы открыть диалоговое окно **Изменить источник данных**, выберите **Файл базы данных Microsoft SQL Server**, и затем нажмите кнопку **ОК**.  
  
5.  Выберите **Обзор**, чтобы найти файл .MDF, содержащий базу данных "Борей".  
  
6.  В зависимости от требований вашей версии базы данных "Борей" выберите **Использовать аутентификацию Windows** или **Аутентификация SQL Server** и введите определенное имя пользователя и определенный пароль для входа на компьютер с запущенной системой SQL Server.  
  
7.  Нажмите кнопку **ОК**.  
  
     Подключение к данным для базы данных "Борей" добавляется в **Обозреватель серверов**\/**Обозреватель баз данных**.  
  
> [!NOTE]
>  В [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] были внесены изменения, затрагивающие файл базы данных "Борей" \(.MDF\).  Дополнительные сведения см. в разделе [Практическое руководство. Установка образцов баз данных](../data-tools/how-to-install-sample-databases.md).  
  
#### Создание подключения к базе данных "Northwind" – файлу базы данных Access \(MDB или ACCDB\)  
  
1.  В меню **Вид** выберите **Обозреватель серверов**\/**Обозреватель баз данных**.  
  
2.  В разделе **Обозреватель серверов**\/**Обозреватель баз данных** откройте контекстное меню элемента **Подключения данных** и выберите команду **Добавить подключение**.  
  
     После выбора элемента **Добавить подключение** отображается диалоговое окно **Выбор источника данных** или диалоговое окно **Добавить подключение**.  
  
3.  В диалоговом окне **Выбор источника данных** выберите **Файл базы данных Microsoft Access** и нажмите кнопку **ОК**.  
  
4.  При отображении диалогового окна **Добавить подключение** убедитесь, что для параметра **Источник данных** задано значение **Файл базы данных Microsoft Access**.  Если значение **Файл базы данных Microsoft Access** не задано, выберите **Изменить**, чтобы открыть диалоговое окно **Изменить источник данных**, выберите **Файл базы данных Microsoft Access**, и затем нажмите кнопку **ОК**.  
  
5.  Выберите **Обзор**, чтобы найти файл .MDB или .ACCDB, содержащий базу данных "Борей".  
  
6.  Введите имя пользователя и пароль, если этого требует ваша версия базы данных "Борей".  
  
7.  Нажмите кнопку **ОК**.  
  
     Подключение к данным для базы данных "Борей" добавляется в **Обозреватель серверов**\/**Обозреватель баз данных**.  
  
## См. также  
 [Практическое руководство. Установка образцов баз данных](../data-tools/how-to-install-sample-databases.md)   
 [Программирование данных в Access 2010](http://msdn.microsoft.com/library/office/ff965871.aspx)   
 [Пошаговые руководства работы с данными](../Topic/Data%20Walkthroughs.md)