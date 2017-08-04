---
title: "Развертывание и безопасность технологии ClickOnce | Microsoft Docs"
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
  - "развертывание ClickOnce"
  - "развертывание приложений [ClickOnce]"
  - "публикация, ClickOnce"
  - "приложения Windows, развертывание ClickOnce"
ms.assetid: abab6d34-c3c2-45c1-a8b6-43c7d3131e7a
caps.latest.revision: 32
caps.handback.revision: 32
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Развертывание и безопасность технологии ClickOnce
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] — это технология развертывания, которая позволяет создавать самообновляющиеся Windows\-приложения, которые можно устанавливать и запускать с минимальным вмешательством со стороны пользователя. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] предоставляет полную поддержку публикации и обновления для приложений, написанных на языках Visual Basic и Visual C\# и развернутых с использованием технологии ClickOnce.  Дополнительные сведения о развертывании приложений Visual C\+\+ см. в разделе [Развертывание с помощью технологии ClickOnce для приложений Visual C\+\+](/visual-cpp/ide/clickonce-deployment-for-visual-cpp-applications).  
  
 Технология [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] предназначена для решения трех основных проблем развертывания:  
  
-   **Трудности обновления приложений.** В случае развертывания с помощью установщика Microsoft Windows всякий раз, когда приложение обновляется, пользователь может установить обновление — MSP\-файл — и применить его к установленному продукту; технология развертывания [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] позволяет предоставлять обновления автоматически.  Загружаются только те части приложения, которые изменились, а затем полное, обновленное приложение повторно устанавливается из новой расположенной рядом папки.  
  
-   **Влияние на компьютер пользователя.** В случае развертывания с помощью установщика Windows приложения часто основаны на общих компонентах, с возможностью конфликтов контроля версий. В технологии развертывания [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] каждое приложение самодостаточно и не оказывает влияния на другие приложения.  
  
-   **Разрешения безопасности.** Развертывание с помощью установщика Windows должно выполняться с правами администратора и допускает только ограниченную пользовательскую установку. Развертывание по технологии [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] предоставляет пользователям, не имеющим прав администратора, возможность установки, и позволяет наделять только теми правами системы безопасности доступа к коду, которые необходимы для приложения.  
  
 В прошлом эти проблемы иногда вынуждали разработчиков принимать решение о создании веб\-приложений вместо Windows\-приложений, принося в жертву простоте установки пользовательский интерфейс с широкими возможностями.  Используя приложения, разворачиваемые по технологии [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], можно использовать преимущества обоих методов.  
  
## Что такое приложение ClickOnce?  
 Приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] — это любое приложение Windows на базе Presentation Foundation \(XBAP\) или Windows Forms \(EXE\), консольное приложение \(EXE\) или решение Office \(DLL\), опубликованное с помощью технологии [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  Приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] можно опубликовать тремя разными способами: с веб\-страницы, из общего сетевого файлового ресурса или с носителя, например компакт\-диска.  Приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] можно устанавливать на компьютер пользователя и запускать локально даже при работе в автономном режиме, либо запускать в интерактивном режиме без постоянной установки каких\-либо компонентов на компьютер пользователя.  Дополнительные сведения см. в разделе [Выбор стратегии развертывания ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 Приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] могут быть самообновляющимися; они могут проверять наличие новых версий по мере их доступности и автоматически заменять любые обновленные файлы.  Разработчик может задать поведение обновления. Сетевой администратор также может управлять стратегиями обновления, например помечая обновление как обязательное.  Конечный пользователь и администратор могут также откатывать обновления к более ранней версии.  Дополнительные сведения см. в разделе [Выбор стратегии обновления ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).  
  
 Поскольку приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] изолированы, установка и выполнение приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] не может нарушить работу существующих приложений.  Приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] самодостаточны, поскольку каждое приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] устанавливается и выполняется из безопасного кэша, выделенного для каждого пользователя и для каждого приложения.  Приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] выполняются в зонах безопасности Интернета или интрасети.  При необходимости приложение может запросить повышенные уровни разрешений.  Дополнительные сведения см. в разделе [Защита приложений ClickOnce](../deployment/securing-clickonce-applications.md).  
  
## Технология ClickOnce и вопросы безопасности  
 В основе механизма обеспечения безопасности технологии [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] лежат сертификаты, политики управления доступом для кода и запросы о доверии ClickOnce.  
  
### Сертификаты  
 Сертификаты Authenticode используются для проверки подлинности издателя приложения.  Использование сертификатов Authenticode для развертывания приложений позволяет ClickOnce предотвратить случаи предоставления вредоносной программы под видом легальной программы, полученной из доверенного источника.  Кроме того, сертификаты можно также использовать для подписывания приложений и манифестов развертывания, чтобы пользователи могли проверить, не были ли файлы изменены злоумышленником.  Дополнительные сведения см. в разделе [ClickOnce и технология Authenticode](../deployment/clickonce-and-authenticode.md).  Сертификаты также можно использовать для настройки на клиентских компьютерах списка надежных издателей.  Если приложение получено от надежного издателя, его можно устанавливать без вмешательства пользователя.  Дополнительные сведения см. в разделе [Общие сведения о развертывании доверенных приложений](../deployment/trusted-application-deployment-overview.md).  
  
### Управление доступом для кода  
 Управление доступом для кода помогает ограничить доступ кода к защищенным ресурсам.  В большинстве случаев для ограничения доступа можно использовать зоны Интернета или локальной интрасети.  Чтобы запросить зону, подходящую для приложения, используйте страницу **Безопасность** в **конструкторе проектов**.  Кроме того, можно выполнять отладку приложений с ограниченными правами для имитации взаимодействия с пользователем.  Дополнительные сведения см. в разделе [Управление доступом для кода для приложения ClickOnce](../deployment/code-access-security-for-clickonce-applications.md).  
  
### Конфигурация запроса о доверии с помощью ClickOnce  
 Если приложение запрашивает больше прав, чем позволяет зона, пользователю можно отправить запрос о доверии.  Пользователь сможет решить, следует ли доверять приложениям ClickOnce \(таким как, например приложениям Windows Forms, Windows Presentation Foundation, консоли, XAML\-приложениям браузера и решениям Office\) и разрешать им выполняться.  Дополнительные сведения см. в разделе [Практическое руководство. Настройка поведения запроса о доверии ClickOnce](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md).  
  
## Как работает развертывание ClickOnce  
 Основная архитектура развертывания [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] основана на двух XML\-файлах манифестов: манифесте приложения и манифесте развертывания.  Файлы используются для описания расположения, из которого выполняется установка приложений ClickOnce, а также способов и времени обновления приложений.  
  
### Публикация приложений ClickOnce  
 Манифест приложения описывает само приложение.  Описание содержит сборки, зависимости и файлы, которые составляют приложение, требуемые разрешения и местоположение, где будут доступны обновления.  Для создания манифеста приложения используется мастер публикаций в Visual Studio или средство создания и изменения манифеста \(Mage.exe\) в [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)].  Дополнительные сведения см. в разделе [Практическое руководство. Публикация приложения ClickOnce с помощью мастера публикации](../Topic/How%20to:%20Publish%20a%20ClickOnce%20Application%20using%20the%20Publish%20Wizard.md).  
  
 Манифест развертывания описывает порядок развертывания приложения.  Описание содержит местоположение манифеста приложения и версию приложения, которая должна запускаться клиентами.  
  
### Развертывание приложений ClickOnce  
 После того как манифест развертывания создан, он копируется в местоположение развертывания.  Это может быть веб\-сервер, общий сетевой файловый ресурс или носитель, такой как компакт\-диск.  Манифест приложения и все файлы приложения копируются также в местоположение развертывания, которое задается в манифесте развертывания.  Это местоположение может совпадать с местоположением развертывания или оно может находиться в другом месте.  При использовании **Мастера публикации** в Visual Studio операции копирования выполняются автоматически.  
  
### Установка приложений ClickOnce  
 После его развертывания в местоположении развертывания конечные пользователи могут загрузить и установить приложение, щелкнув значок, представляющий файл манифеста развертывания на веб\-странице или в папке.  В большинстве случаев для конечного пользователя выводится простое диалоговое окно с запросом на подтверждение установки, после которого выполняется установка, и приложение запускается без дополнительных действий пользователя.  Если приложению требуются повышенные разрешения или приложение не подписано с помощью доверенного сертификата, перед продолжением установки также выводится диалоговое окно с запросом на предоставление разрешения.  Несмотря на то, что при использовании технологии ClickOnce приложения устанавливаются для учетной записи конкретного пользователя, повышение прав может потребоваться при наличии необходимых компонентов, для установки которых требуются права администратора.  Дополнительные сведения о повышенных разрешениях см. в разделе [Защита приложений ClickOnce](../deployment/securing-clickonce-applications.md).  
  
 Сертификаты могут быть доверенными на уровне компьютера или предприятия, поэтому приложения ClickOnce, подписанные с использованием доверенного сертификата, можно устанавливать в автоматическом режиме.  Дополнительные сведения о доверенных сертификатах см. в разделе [Общие сведения о развертывании доверенных приложений](../deployment/trusted-application-deployment-overview.md).  
  
 Приложение можно добавить в меню **Пуск** конкретного пользователя и в группу **Установка и удаление программ** в **Панели управления**.  В отличие от других технологий развертывания в папку **Program Files** и реестр ничего не добавляется. Для установки приложений права администратора не требуются.  
  
> [!NOTE]
>  Имеется также возможность запретить добавление приложения в меню **Пуск** и в группу **Установка и удаление программ**, в действительности заставляя приложение вести себя как какое\-нибудь веб\-приложение.  Дополнительные сведения см. в разделе [Выбор стратегии развертывания ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
### Обновление приложений ClickOnce  
 При создании обновленной версии приложения создается новый манифест приложения, а файлы копируются в расположение развертывания \(как правило, во вложенную папку папки, из которой было развернуто исходное приложение\).  Администратор обновляет манифест развертывания, чтобы нацелить его на местоположение новой версии приложения.  
  
> [!NOTE]
>  Для выполнения этих шагов можно использовать **Мастер публикаций** в Visual Studio.  
  
 Помимо местоположения развертывания манифест развертывания содержит также местоположение обновления \(веб\-страницу или общий сетевой файл\).  Чтобы указать время и периодичность проверки приложением наличия обновлений, используются свойства **Publish** приложения [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  Поведение обновления может быть задано в манифесте развертывания, или оно может быть представлено в виде вариантов выбора в пользовательском интерфейсе приложения с помощью функций API [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  Кроме того, свойства пункта **Публикация** могут использоваться, чтобы сделать обновления обязательными или чтобы откатить их назад к более ранней версии.  Дополнительные сведения см. в разделе [Выбор стратегии обновления ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).  
  
### Установщики компонентов сторонних производителей  
 Для совместной установки приложения и компонентов сторонних производителей можно использовать установщик ClickOnce.  Для этого потребуется распространяемый пакет \(EXE\- или MSI\-файл\), который нужно описать с помощью манифеста продукта, не зависящего от языка, а также манифест пакета, содержащий метаданные для конкретного языка.  Дополнительные сведения см. в разделе [Создание пакетов загрузчика](../deployment/creating-bootstrapper-packages.md).  
  
## Средства ClickOnce  
 В следующей таблице описаны средства, которые можно использовать для создания, изменения, подписывания и повторного подписывания манифестов приложений и развертываний.  
  
|Средство|Описание|  
|--------------|--------------|  
|[Страница "Безопасность" в конструкторе проектов](../ide/reference/security-page-project-designer.md)|Используется для подписывания манифестов приложений и развертываний.|  
|[Страница публикации в конструкторе проектов](../ide/reference/publish-page-project-designer.md)|Используется для создания и изменения манифестов приложений и развертываний для приложений на Visual Basic и Visual C\#.|  
|[Mage.exe \(средство создания и редактирования манифеста\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)|Используется для создания манифестов приложений и развертываний для приложений на Visual Basic, Visual C\# и Visual C\+\+.<br /><br /> Используется для подписывания \(и повторного подписывания\) манифестов приложений и развертываний.<br /><br /> Поддерживает запуск из пакетных скриптов и командной строки.|  
|[MageUI.exe \(Manifest Generation and Editing Tool, Graphical Client\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)|Используется для создания и изменения манифестов приложений и развертываний.<br /><br /> Используется для подписывания \(и повторного подписывания\) манифестов приложений и развертываний.|  
|[Задача GenerateApplicationManifest](../msbuild/generateapplicationmanifest-task.md)|Используется для создания манифестов приложений.<br /><br /> Поддерживает запуск из MSBuild.  Дополнительные сведения см. в разделе [Справочные сведения о MSBuild](../msbuild/msbuild-reference.md).|  
|[Задача GenerateDeploymentManifest](../msbuild/generatedeploymentmanifest-task.md)|Используется для создания манифестов развертываний.<br /><br /> Поддерживает запуск из MSBuild.  Дополнительные сведения см. в разделе [Справочные сведения о MSBuild](../msbuild/msbuild-reference.md).|  
|[Задача SignFile](../msbuild/signfile-task.md)|Используется для подписывания манифестов приложений и развертываний.<br /><br /> Поддерживает запуск из MSBuild.  Дополнительные сведения см. в разделе [Справочные сведения о MSBuild](../msbuild/msbuild-reference.md).|  
|<xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities>|Используется для разработки собственных приложений, создающих манифесты приложений и развертываний.|  
  
 В следующей таблице приведены браузеры и версии платформы .NET Framework, требуемые для поддержки приложений ClickOnce в них.  
  
|Браузер|Версия платформы .NET Framework|  
|-------------|-------------------------------------|  
|Internet Explorer|2.0, 3.0, 3.5, 3.5 с пакетом обновления 1 \(SP1\), 4|  
|Firefox|2.0 с пакетом обновления 1 \(SP1\), 3.5 с пакетом обновления 1 \(SP1\), 4|  
  
## См. также  
 [Развертывание ClickOnce в Windows Vista](../deployment/clickonce-deployment-on-windows-vista.md)   
 [Публикация ClickOnce\-приложений](../deployment/publishing-clickonce-applications.md)   
 [Защита приложений ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Развертывание компонентов COM с помощью ClickOnce](../deployment/deploying-com-components-with-clickonce.md)   
 [Построение ClickOnce\-приложений из командной строки](../deployment/building-clickonce-applications-from-the-command-line.md)   
 [Отладка ClickOnce\-приложений, использующих System.Deployment.Application](../deployment/debugging-clickonce-applications-that-use-system-deployment-application.md)