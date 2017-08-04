---
title: "Практическое руководство. Создание локализованного пакета загрузчика | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "зависимости, создание локализованных пакетов загрузчика"
  - "локализованные пакеты загрузчика"
  - "необходимые компоненты, создание локализованных пакетов загрузчика"
ms.assetid: 66a1bc7e-6540-4164-963d-557196a69d8a
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Создание локализованного пакета загрузчика
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Закончив создание пакета начального загрузчика, вы можете сформировать его локализованные версии, создав по два или несколько файлов для каждого языкового стандарта: файл условий лицензионного соглашения на использование программного обеспечения \(например, eula.rtf\) и манифест пакета \(package.xml\).  
  
 По умолчанию в Visual Studio 2010 локализованные пакеты начальной загрузки включены только для .NET Framework 4, .NET Framework 4 Client Profile, F\# Runtime 2.0 и F\# Runtime 4.0.  Чтобы создать локализованные пакеты для других начальных загрузчиков, сделайте следующее.  
  
1.  Создайте папку с названием языкового стандарта в директории \\Program Files\\Microsoft SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages\\*BootstrapperPackageName*.  
  
2.  Создайте файл, содержащий условия лицензионного соглашения на использование программного обеспечения, для пакета начального загрузчика и сохраните его в новую папку.  
  
3.  Создайте манифест пакета с именем package.xml, обновите строки и культуру и сохраните файл в новую папку.  Если вы уже создали начальный загрузчик для Visual Studio с целевым зыком, на этом этапе можно просто скопировать файл Visual Studio package.xml и внести в него необходимые изменения.  
  
> [!NOTE]
>  Если для развертывания приложений используется проект установки, приложение можно локализовать, изменив свойство **Локализация**.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### Создание пакета локализованного начального загрузчика  
  
1.  Создайте папку с именем, соответствующим языковому стандарту.  
  
     На 32\-разрядных компьютерах эту папку необходимо создать в директории \\Program Files\\Microsoft SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages\\*BootstrapperPackageName*\\.  
  
     На 64\-разрядных компьютерах — в директории \\Program Files \(86\)\\Microsoft SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages\\*BootstrapperPackageName*\\.  
  
     В следующей таблице показано, какие имена папок можно использовать для соотнесения с языковым стандартом.  
  
    |Языковой стандарт|Имя папки|  
    |-----------------------|---------------|  
    |Китайский \(упрощенный\)|zh\-Hans|  
    |Китайский \(традиционный\)|zh\-Hant|  
    |Чешский|cs|  
    |Немецкий|de|  
    |Английский|en|  
    |Испанский|es|  
    |Французский|fr|  
    |Итальянский|it|  
    |Корейский|ko|  
    |Японский|ja|  
    |Польский|pl|  
    |Португальский \(Бразилия\)|pt\-BR|  
    |Русский|ru|  
    |Турецкий|tr|  
  
2.  Создайте файл, содержащий условия лицензионного соглашения на использование программного обеспечения, для пакета начального загрузчика и сохраните его в новую папку.  
  
3.  Создайте манифест пакета с именем package.xml и сохраните его в новую папку.  Для получения дополнительной информации см. [Практическое руководство. Создание манифеста пакета](../deployment/how-to-create-a-package-manifest.md).  
  
4.  Обновите раздел `<Strings>` манифеста пакета, так чтобы язык строк соответствовал языковому стандарту.  
  
5.  Измените значение `<String Name="Culture">` таким образом, чтобы оно соответствовало имени папки.  
  
6.  Сохраните файл package.xml.  
  
### Создание пакета начального загрузчика для .NET Framework 3.5 Service Pack 1 с локализацией на французском языке  
  
1.  Создайте папку с именем fr.  Имя папки должно совпадать с именем языкового стандарта.  
  
     На 32\-разрядных компьютерах эту папку необходимо создать в директории \\Program Files\\Microsoft SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages\\DotNetFX35SP1\\.  
  
     На 64\-разрядных компьютерах — в директории \\Program Files \(86\)\\Microsoft SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages\\DotNetFX35SP1\\.  
  
2.  Сохраните локализованную версию условий лицензионного соглашения на использование программного обеспечения в папку с именем fr.  
  
3.  Скопируйте файл \\Program Files \(x86\)\\Microsoft SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages\\DotNetFX35SP1\\en\\package.xml в папку с именем fr и откройте его в программе XML Designer.  
  
4.  Обновите раздел `<Strings>` манифеста пакета, так чтобы строки с сообщениями об ошибках были на французском языке.  
  
5.  Измените значение `<String Name="Culture">` на fr.  
  
6.  Сохраните файл package.xml.  
  
## См. также  
 [Создание пакетов загрузчика](../deployment/creating-bootstrapper-packages.md)   
 [Предварительные условия для развертывания приложения](../deployment/application-deployment-prerequisites.md)   
 [Практическое руководство. Создание манифеста пакета](../deployment/how-to-create-a-package-manifest.md)