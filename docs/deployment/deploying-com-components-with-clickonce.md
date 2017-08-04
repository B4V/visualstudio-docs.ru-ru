---
title: "Развертывание компонентов COM с помощью ClickOnce | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "развертывание ClickOnce, компоненты COM"
  - "компоненты COM, развертывание"
  - "компоненты, развертывание"
  - "развертывание приложений [ClickOnce], компоненты COM"
  - "COM-развертывание без регистрации"
ms.assetid: 1a4c7f4c-7a41-45f2-9af4-8b1666469b89
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 12
---
# Развертывание компонентов COM с помощью ClickOnce
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Развертывание устаревших компонентов COM всегда было трудной задачей.  Компоненты должны быть глобально зарегистрированы и, таким образом, могут вызывать нежелательный побочный эффект между перекрывающимися приложениями.   Такая ситуация для приложений в .NET Framework обычно не представляет проблемы, поскольку компоненты являются совершенно изолированными или параллельно совместимыми.  Visual Studio позволяет развертывать изолированные компоненты COM в Windows XP или более поздней версии операционной системы.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] предоставляет несложный и безопасный механизм развертывания приложений .NET.  Но если приложение использует устаревшие компоненты COM, для его развертывания необходимо предпринять дополнительные шаги.  В этом разделе описывается, как развертывать изолированные компоненты COM и выполнять ссылку на собственные компоненты \(например, из Visual Basic 6.0 или Visual C\+\+\).  
  
 Дополнительные сведения о развертывании компонентов COM см. на странице "Упрощение развертывания приложения при помощи [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] COM\-взаимодействия без регистрации" на веб\-узле [http:\/\/msdn.microsoft.com\/msdnmag\/issues\/05\/04\/RegFreeCOM\/default.aspx](http://msdn.microsoft.com/msdnmag/issues/05/04/RegFreeCOM/default.aspx).  
  
## COM\-взаимодействие без регистрации  
 COM\-взаимодействие без регистрации является новой технологией развертывания и активации изолированных компонентов COM.  При такой технологии все сведения о библиотеке типов и регистрации компонентов, обычно устанавливаемые в системный реестр, вставляются в XML\-файл, называемый манифестом и хранящийся в той же папке, что и приложение.  
  
 Для изолированного компонента COM требуется, чтобы он был зарегистрирован на машине разработчика, но он не должен быть зарегистрирован на компьютере конечного пользователя.  Чтобы изолировать компонент COM, все что требуется — это присвоить его свойству ссылки **Isolated** значение **True**.  По умолчанию для этого свойства установлено значение **False**, указывая, что эту ссылку нужно рассматривать как зарегистрированную ссылку COM.  Если значением этого свойства является **True**, это вызывает создание манифеста для этого компонента во время построения.  Это также вызывает копирование соответствующих файлов в папку приложения во время установки.  
  
 Когда генератор манифеста встречает изолированную ссылку COM, он нумерует все элементы `CoClass` в библиотеке типов компонентов, сопоставляя каждый элемент с соответствующими данными регистрации и создавая определения манифеста для всех классов COM в файле библиотеки типов.  
  
## Развертывание компонентов COM\-взаимодействия без регистрации с помощью ClickOnce  
 Технология развертывания [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] хорошо подходит для развертывания изолированных компонентов COM, потому что [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] и COM\-взаимодействие без регистрации требуют наличия манифеста для развертывания компонентов.  
  
 Как правило, автор компонента должен предоставлять манифест.  Если манифест не предоставляется, Visual Studio может автоматически создать манифест для компонента COM.  Создание манифеста выполняется во время процесса публикации [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]; дополнительные сведения см. в разделе [Публикация ClickOnce\-приложений](../deployment/publishing-clickonce-applications.md).  Эта возможность позволяет также использовать устаревшие компоненты, созданные в предыдущих средах разработки, таких как Visual Basic 6.0.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] может развертывать компоненты COM двумя способами:  
  
-   Использование загрузчика для развертывания компонентов COM; этот способ применим на всех поддерживаемых платформах.  
  
-   Использование развертывания с изоляцией собственного компонента \(называемой также COM\-взаимодействием без регистрации\).  Но этот способ будет работать только в Windows XP или более поздней версии операционной системы.  
  
### Пример изоляции и развертывания простого компонента COM  
 Чтобы продемонстрировать развертывание компонента COM\-взаимодействия без регистрации, в этом примере в Visual Basic создается приложение Windows, которое ссылается на собственный изолированный компонент COM, созданный с использованием Visual Basic 6.0, а затем это приложение развертывается с использованием [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  
  
 Вначале необходимо создать собственный компонент COM.  
  
##### Создание собственного компонента COM  
  
1.  Используя Visual Basic 6.0, из меню **Файл** последовательно выберите **Создать**, затем **Проект**.  
  
2.  В диалоговом окне **Новый проект** выберите узел **Visual Basic** и выберите проект **ActiveX DLL**.  В поле **Имя** введите `VB6Hello`.  
  
    > [!NOTE]
    >  COM\-взаимодействие без регистрации поддерживает только типы проектов ActiveX DLL и элемента ActiveX; типы проектов ActiveX EXE и документа ActiveX не поддерживаются.  
  
3.  В **обозревателе решений** дважды щелкните **Class1.vb**, чтобы открыть текстовый редактор.  
  
4.  В Class1.vb добавьте следующий код после созданного кода для метода `New`:  
  
    ```  
    Public Sub SayHello()  
       MsgBox "Message from the VB6Hello COM component"  
    End Sub  
    ```  
  
5.  Постройте компонент.  В меню **Построение** выберите команду **Построить решение**.  
  
> [!NOTE]
>  COM\-взаимодействие без регистрации поддерживает только типы проектов элементов управления DLL и COM.  С COM\-взаимодействием без регистрации нельзя использовать типы проекта EXE.  
  
 Теперь можно создать приложение Windows и добавить в него ссылку на компонент COM.  
  
##### Создание приложения Windows с использованием компонента COM  
  
1.  Используя Visual Basic, в меню **Файл** последовательно выберите **Создать**, а затем **Проект**.  
  
2.  В диалоговом окне **Создание проекта** выберите узел **Visual Basic** и выберите **Приложение Windows**.  В поле **Имя** введите `RegFreeComDemo`.  
  
3.  В **обозревателе решений** нажмите кнопку **Показать все файлы** для отображения ссылок на проекты.  
  
4.  Щелкните правой кнопкой мыши узел **Ссылки** и выберите из контекстного меню команду **Добавить ссылку**.  
  
5.  В диалоговом окне **Добавление ссылки** перейдите на вкладку **Обзор**, перейдите к библиотеке VB6Hello.dll, затем выберите ее.  
  
     В списке "Ссылки" появится ссылка **VB6Hello**.  
  
6.  Наведите указатель на **панель элементов**, выберите элемент управления **Button** и перетащите его на форму **Form1**.  
  
7.  В окне **Свойства** задайте для свойства кнопки **Text** значение "Привет".  
  
8.  Дважды нажмите кнопку, чтобы добавить код обработчика, и в файле кода добавьте следующий код:  
  
    ```  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
        Dim VbObj As New VB6Hello.Class1  
        VbObj.SayHello()  
    End Sub  
    ```  
  
9. Запустите приложение.  В меню **Отладка** выберите команду **Начать отладку**.  
  
 Далее необходимо изолировать элемент.  Каждый компонент COM, который использует приложение, представлен в проекте как ссылка COM.  Эти ссылки видны под узлом **Ссылки** в окне **Обозреватель решений**.  \(Следует отметить, что ссылки можно добавлять либо непосредственно с использованием команды **Добавить ссылку** в меню **Проект**, либо косвенно, перетаскивая в форму элемент управления ActiveX\).  
  
 Следующие шаги демонстрируют, как изолировать компонент COM и опубликовать обновленное приложение, содержащее изолированный элемент управления.  
  
##### Изолирование компонента COM  
  
1.  В **обозревателе решений**, в узле **Ссылки** выберите ссылку **VB6Hello**.  
  
2.  В окне **Свойства** измените значение свойства **Isolated** с **False** на **True**.  
  
3.  В меню **Построение** выберите команду **Построить решение**.  
  
 Теперь после нажатия клавиши F5 приложение работает, как предполагалось, но теперь оно работает при COM\-взаимодействии без регистрации.  Для проверки попытайтесь отменить регистрацию компонента VB6Hello.dll и запустить RegFreeComDemo1.exe вне среды IDE Visual Studio.  Теперь при нажатии кнопки приложение продолжает работать.  Если временно переименовать манифест приложения, оно вновь завершится с ошибкой.  
  
> [!NOTE]
>  Можно смоделировать отсутствие компонента COM, временно отменив его регистрацию.  Откройте командную строку, перейдите в системную папку, введя строку `cd /d %windir%\system32`, а затем отмените регистрацию компонента, введя строку `regsvr32 /u VB6Hello.dll`.  Его регистрацию можно вновь включить, введя `regsvr32 VB6Hello.dll`.  
  
 Последним шагом является публикация приложения при помощи [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]:  
  
##### Публикация обновления приложения с изолированным компонентом COM  
  
1.  Из меню **Построение** выберите команду **Опубликовать RegFreeComDemo**.  
  
     Откроется мастер публикации.  
  
2.  В мастере публикации укажите местоположение на локальном диске компьютера, где можно проверить опубликованные файлы.  
  
3.  Нажмите кнопку **Готово**, чтобы опубликовать приложение.  
  
 При проверке опубликованных файлов вы обратите внимание, что включен файл sysmon.ocx.  Элемент управления совершенно изолирован от этого приложения. Это означает, что если на машине конечного пользователя имеется другое приложение, использующее другую версию элемента управления, оно не сможет повлиять на данное приложение.  
  
## Создание ссылок на собственные сборки  
 Visual Studio поддерживает ссылки на собственные сборки Visual Basic 6.0 или C\+\+; такие ссылки называются собственными ссылками.  Сказать, является ли ссылка собственной, можно при проверке, установлено ли для свойства **File Type** значение **Native** или **ActiveX**.  
  
 Чтобы добавить собственную ссылку, используется команда **Добавить ссылку**, после чего производится переход к местоположению манифеста.  Некоторые компоненты помещают манифест внутри библиотеки DLL.  В этом случае можно просто выбрать саму библиотеку DLL, и Visual Studio добавит ее как собственную ссылку, если будет обнаружено, что компонент содержит внедренный манифест.  Visual Studio также автоматически включит зависимые файлы или сборки, перечисленные в манифесте, если они находятся в той же папке, что и компонент, на который производится ссылка.  
  
 Изоляция элемента управления COM облегчает развертывание компонентов COM, которые еще не имеют манифестов.  Но если компонент снабжен манифестом, на манифест можно ссылаться непосредственно.  На самом деле необходимо по мере возможности всегда использовать манифест, предоставляемый автором компонента, а не использовать свойство **Isolated**.  
  
## Ограничение развертывания компонента COM\-взаимодействия без регистрации  
 COM\-взаимодействие без регистрации имеет явные преимущества перед традиционной техникой развертывания.  Однако имеется ряд ограничений и моментов, на которые следует также обратить внимание.  Самое большое ограничение заключается в том, что указанный подход работает только в Windows XP или операционных системах более поздних версий.  Для реализации COM\-взаимодействия без регистрации требуются изменения способа загрузки компонентов в базовую операционную систему.   К сожалению, для COM\-взаимодействия без регистрации нет поддержки нижнего уровня.  
  
 Не каждый компонент подходит в качестве возможного COM\-взаимодействия без регистрации.  Компонент не подходит, если выполняется какое\-либо из следующих условий.  
  
-   Компонент является внепроцессным сервером.  Серверы EXE не поддерживаются; поддерживаются только библиотеки DLL.  
  
-   Компонент является частью операционной системы или является компонентом системы, таким как XML, Internet Explorer или MDAC.  Необходимо соблюдать политику распространения, которую требует автор компонента; проконсультируйтесь у своего поставщика.  
  
-   Компонент является частью приложения, такого как Microsoft Office.  Например, не пытайтесь изолировать объектную модель Microsoft Excel.  Это часть Office, которая может использоваться только в компьютерах с установленным полным продуктом Office.  
  
-   Компонент предназначен для использования как надстройка, например надстройка Office или элемент управления в веб\-браузере.  Для таких компонентов обычно требуется схема регистрации, определенная средой размещения, выходящей за область самого манифеста.  
  
-   Компонент управляет физическим или виртуальным устройством системы, например драйвером устройства для диспетчера очереди печати.  
  
-   Компонент является распространяемым компонентом доступа к данным.  Для приложений обработки данных обычно требуется отдельный распространяемый компонент доступа к данным, который должен быть установлен перед запуском приложения.  Не пытайтесь изолировать компоненты, такие как элемент управления ADO \(Microsoft\), Microsoft OLE DB или MDAC.  Вместо этого, если приложение использует MDAC или SQL Server Express, необходимо устанавливать их как необходимые компоненты; см. раздел [Практическое руководство. Установка необходимых компонентов при помощи ClickOnce\-приложения](../Topic/How%20to:%20Install%20Prerequisites%20with%20a%20ClickOnce%20Application.md).  
  
 В некоторых случаях разработчик компонента может иметь возможность изменить его для COM\-взаимодействия без регистрации.  Если это невозможно, можно строить и публиковать зависящие от них приложения через стандартную схему регистрации с помощью установщика.  Дополнительные сведения см. в разделе [Создание пакетов загрузчика](../deployment/creating-bootstrapper-packages.md).  
  
 Компонент COM может быть изолирован в приложении только один раз.  Например, нельзя изолировать один и тот же компонент COM из двух разных проектов **библиотеки классов**, являющихся частью одного приложения,  так как это приводит к созданию предупреждения, и приложению не удастся выполнить загрузку во время исполнения.  Чтобы избежать этой проблемы, корпорация Майкрософт рекомендует инкапсулировать компоненты COM в одной библиотеке классов.  
  
 Имеется несколько сценариев, в которых регистрация COM необходима на машине разработчика, даже если для развертывания приложения регистрация не требуется.  Свойство `Isolated` требует, чтобы компонент COM был зарегистрирован на машине разработчика, чтобы автоматически создавать манифест во время построения.  Нет возможности определения регистрации, вызывающего самостоятельную регистрацию во время построения.  Кроме того, классы, не определенные явно в библиотеке типов, не будут отражены в манифесте.  При использовании компонента COM с уже существующим манифестом, таким как собственная ссылка, для компонента не нужна регистрация во время выполнения.  Но регистрация требуется, если компонент является элементом управления ActiveX и необходимо его включить в **панель элементов** и в конструктор Windows Forms.  
  
## См. также  
 [Развертывание и безопасность технологии ClickOnce](../deployment/clickonce-security-and-deployment.md)