---
title: "Доступ к локальным и удаленным данным в приложениях ClickOnce | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce — развертывание, данные"
  - "доступ к данным, приложения ClickOnce"
ms.assetid: be5cbe12-6cb6-49c9-aa59-a1624e1eef3d
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Доступ к локальным и удаленным данным в приложениях ClickOnce
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Большинство приложений потребляют или производят данные.[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] предоставляет разнообразные методы чтения и записи данных как локально, так и удаленно.  
  
## Локальные данные  
 В [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] можно загружать и хранить данные локально, используя любой из следующих методов.  
  
-   Каталог данных [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]  
  
-   Изолированное хранилище  
  
-   Другие локальные файлы  
  
### Каталог данных ClickOnce  
 Каждое установленное на локальном компьютере приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] имеет каталог данных, который сохранен в папке пользователя Documents and Settings. Любой файл, включенный в приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] и помеченный как файл «данных», копируется в этот каталог при установке приложения. Файлы данных могут представлять собой данные любого типа. Чаще всего используются текстовые файлы, файлы XML и файлы базы данных, например MDB\-файлы Microsoft Access.  
  
 Каталог данных предназначен для управляемых приложением данных, то есть данных, которые приложение явно сохраняет и обслуживает. Все статические, независимые файлы, которые не помечены как «данные» в манифесте приложения, помещаются в каталог приложения. В этом же каталоге находятся исполняемые файлы приложения \(.exe\) и сборки.  
  
> [!NOTE]
>  Если приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] удаляется, его каталог данных также удаляется. Никогда не используйте каталог данных для хранения управляемых конечным пользователем данных, например документов.  
  
#### Маркировка файлов данных в рассылке ClickOnce  
 Чтобы поместить существующий файл внутрь каталога данных, необходимо пометить существующий файл как файл данных в файле манифеста приложения вашего приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Для получения дополнительной информации см. [Практическое руководство. Включение файла данных в приложение ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
#### Чтение и запись в каталоге данных  
 Для чтения из каталога данных нужно, чтобы приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] запросило разрешение на чтение; аналогично для записи в каталог требуется разрешение на запись. Ваше приложение получит это разрешение автоматически, если оно настроено для работы с полным доверием. Дополнительные сведения о повышении уровня разрешений приложения с использованием технологии повышения уровня разрешений или развертывания надежных приложений см. в разделе [Защита приложений ClickOnce](../deployment/securing-clickonce-applications.md).  
  
> [!NOTE]
>  Если в организации не используется развертывание надежных приложений и отключено повышение уровня разрешений, подтверждение разрешений завершится ошибкой.  
  
 Получив эти разрешения, ваше приложение сможет осуществлять доступ в каталог данных, используя вызовы метода в классах типа <xref:System.IO>. Можно получить путь к каталогу данных в приложении [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] в Windows Forms, воспользовавшись свойством <xref:System.Deployment.Application.ApplicationDeployment.DataDirectory%2A>, определенным в свойстве <xref:System.Deployment.Application.ApplicationDeployment.CurrentDeployment%2A> развертывания <xref:System.Deployment.Application.ApplicationDeployment>. Это самый удобный и рекомендуемый способ доступа к данным. В следующем примере кода показано, как сделать это для текстового файла CSV.txt, включенного вами в развертывание в качестве файла данных.  
  
 [!CODE [ClickOnce.OpenDataFile#1](../CodeSnippet/VS_Snippets_Winforms/ClickOnce.OpenDataFile#1)]  
  
 Дополнительные сведения о маркировке файлов в развертывании как файлов данных см. в разделе [Практическое руководство. Включение файла данных в приложение ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
 Можно также получить путь к каталогу данных, используя соответствующие переменные в классе <xref:System.Windows.Forms.Application>, например <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A>.  
  
 Для выполнения операций с другими типами файлов могут потребоваться дополнительные разрешения. Например, если требуется использовать файл базы данных Access \(.mdb\), приложение должно подтвердить полное доверие, чтобы использовать релевантные классы <xref:System.Data>.  
  
#### Каталог данных и версии приложения  
 Каждая версия приложения имеет свой собственный каталог данных, который изолирован от других версий.[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] создает этот каталог, независимо от того, включены ли в развертывание какие\-либо файлы данных, чтобы приложению было доступно местоположение для создания новых файлов данных во время выполнения. При установке новой версии приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] копирует все существующие файлы данных из каталога данных предыдущей версии в каталог данных новой версии независимо от того, были ли они включены в первоначальное развертывание или созданы приложением.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] заменяет старую версию файла новой версией сервера, если значение хэша для файла данных в старой версии приложения отличается от значения в новой. Кроме того, если в более ранней версии приложения был создан новый файл, который имеет то же имя, что и файл, включенный в развертывание новой версии, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] перезапишет файл старой версии и использует новый. В обоих случаях старые файлы будут включены в подкаталог внутри каталога данных с именем `.pre`, так что приложение по\-прежнему будет иметь доступ к старым данным в целях миграции.  
  
 Если требуется более контролируемая миграция данных, можно использовать API развертывания [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], чтобы выполнить пользовательскую миграцию из старого каталога данных в новый. Необходимо будет проверить наличие доступной загрузки, воспользовавшись свойством <xref:System.Deployment.Application.ApplicationDeployment.IsFirstRun%2A>, загрузить обновление с использованием <xref:System.Deployment.Application.ApplicationDeployment.Update%2A> или <xref:System.Deployment.Application.ApplicationDeployment.UpdateAsync%2A>, а затем самостоятельно выполнить действия по пользовательской миграции данных по окончании обновления.  
  
### Изолированное хранилище  
 Изолированное хранилище предоставляет API для создания файлов с использованием простого API и осуществления доступа к ним. Фактическое расположение хранимых файлов скрыто от разработчика и пользователя.  
  
 Изолированное хранилище работает во всех версиях [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Изолированное хранилище также работает в приложениях с частичным доверием, предоставлять дополнительные разрешения не требуется. Изолированное хранилище следует использовать, если приложение должно выполняться с частичным доверием, но при этом обслуживать данные приложения.  
  
 Для получения дополнительной информации см. [Изолированное хранилище](../Topic/Isolated%20Storage.md).  
  
### Другие локальные файлы  
 Если приложение должно работать с данными конечных пользователей или сохранять такие данные \(отчеты, изображения, музыку и т. д.\), приложению потребуется разрешение <xref:System.Security.Permissions.FileIOPermission> для чтения и записи данных в локальной файловой системе.  
  
## Удаленные данные  
 На некотором этапе приложению, скорее всего, необходимо будет извлечь сведения с удаленного веб\-сайта, например клиентские данные или информацию о рынке. В этом разделе рассматриваются наиболее распространенные методы получения удаленных данных.  
  
### Доступ к файлам по протоколу HTTP  
 Доступ к данным на веб\-сервере можно осуществлять с использованием класса <xref:System.Net.WebClient> или <xref:System.Net.HttpWebRequest> в пространстве имен <xref:System.Net>. Эти данные могут представлять собой статичные файлы или приложения [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], возвращающие необработанные текстовые данные или данные XML. Если формат данных отличается от XML, самым быстрым способом извлечения данных будет использование класса <xref:System.Xml.XmlDocument>, метод <xref:System.Xml.XmlDocument.Load%2A> которого принимает URL\-адрес в качестве аргумента. Пример см. в разделе [Считывание XML\-документа в DOM](../Topic/Reading%20an%20XML%20Document%20into%20the%20DOM.md).  
  
 Необходимо помнить о соображениях безопасности, когда приложение осуществляет доступ к удаленным данным через HTTP. По умолчанию доступ вашего приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] к сетевым ресурсам может быть ограничен в зависимости от использованного способа развертывания приложения. Эти ограничения применяются, чтобы не допустить доступа вредоносных программ к привилегированным удаленным данным или использования компьютера пользователя для атаки на другие компьютеры в сети.  
  
 В следующей таблице перечислены стратегии развертывания, которые можно использовать, и их разрешения в Интернете по умолчанию.  
  
|Тип развертывания|Сетевые разрешения по умолчанию|  
|-----------------------|-------------------------------------|  
|Веб\-установка|Имеется доступ только к веб\-серверу, с которого было установлено приложение|  
|Установка общей папки|Отсутствует доступ к веб\-серверам|  
|Установка с компакт\-диска|Доступны любые веб\-серверы|  
  
 Если приложению [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] не удается получить доступ к веб\-серверу из\-за ограничений безопасности, приложение должно подтвердить <xref:System.Net.WebPermission> для этого веб\-сайта. Дополнительные сведения о повышении уровня разрешений безопасности для приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] см. в разделе [Защита приложений ClickOnce](../deployment/securing-clickonce-applications.md).  
  
### Доступ к данным через веб\-службу XML  
 Если предоставить данные в качестве веб\-службы XML, можно осуществлять доступ к этим данным с помощью прокси\-сервера веб\-службы XML. Прокси\-сервер является классом [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], созданным с помощью любого приложения [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Операции веб\-службы XML, такие как извлечение клиентов, размещение заказов и т. д., предоставляются как методы прокси\-сервера. Благодаря этому пользоваться веб\-службами гораздо проще, чем обычным текстом или файлами XML.  
  
 Если ваш веб\-служба XML работает по протоколу HTTP, в отношении нее будут действовать те же ограничения безопасности, как и в отношении классов <xref:System.Net.WebClient> и <xref:System.Net.HttpWebRequest>.  
  
### Непосредственный доступ к базе данных  
 Можно использовать классы в пространстве имен <xref:System.Data> для установки прямого подключения к серверу базы данных, например SQL Server в сети, однако при этом необходимо учитывать соображения безопасности. В отличие от HTTP\-запросов запросы на подключение к базе данных всегда запрещены по умолчанию в режиме частичного доверия; такие разрешения будут предоставлены по умолчанию, только если приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] устанавливается с компакт\-диска. Это обеспечивает приложению полный уровень доверия. Чтобы включить доступ к конкретной базе данных SQL Server, приложение должно запросить для него разрешение <xref:System.Data.SqlClient.SqlClientPermission>; чтобы включить доступ к базе данных, отличной от БД SQL Server, необходимо запросить разрешение <xref:System.Data.OleDb.OleDbPermission>.  
  
 В большинстве случаев осуществлять прямой доступ к базе данных не потребуется, поскольку доступ осуществляется через приложение веб\-сервера, созданное в [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] или веб\-службе XML. Такой доступ к базе данных часто является оптимальным подходом, если приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] развертывается с веб\-сервера. Доступ к серверу с частичным доверием можно осуществлять без повышения уровня разрешений вашего приложения.  
  
## См. также  
 [Практическое руководство. Включение файла данных в приложение ClickOnce](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md)