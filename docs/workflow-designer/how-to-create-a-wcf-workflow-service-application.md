---
title: "Как создать приложение службы рабочего процесса WCF | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 12d675ac-27d8-4d86-ba16-6f7688f8c841
caps.latest.revision: 14
caps.handback.revision: 14
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# Как создать приложение службы рабочего процесса WCF
[!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] служебные приложения рабочего потока представляют собой распределенные службы коммуникаций, которые передают сообщения клиентам и обратно, из одного процесса в другой.В [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] реализация контракта службы на стороне службы выполняется декларативно с помощью действий рабочего процесса способом, аналогичным тому, который реализован в службах рабочих процессов .NET Framework 3.5.  
  
### Создание сервисного приложения рабочего процесса WCF  
  
1.  Запустите среду [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)].  
  
2.  В меню **Файл** укажите пункт **Создать** и выберите пункт **Проект**.  
  
     Откроется диалоговое окно **Новый проект**.  
  
3.  В области **Установленные шаблоны** выберите категорию **WCF** или **Рабочий процесс** в группе проектов **Visual C\#** или **Visual Basic** \(в зависимости от выбранного языка программирования\).  
  
4.  В средней области выберите **Сервисное приложение рабочего процесса WCF**.  
  
5.  В поле **Имя** введите описательное имя проекта, чтобы облегчить его определение.  
  
6.  В поле **Расположение** введите путь к папке, где будет сохранен проект, или нажмите кнопку **Обзор**, чтобы перейти в эту папку.  
  
7.  В поле **Решение** укажите, создавать ли новое решение, и нажмите кнопку **ОК**.  
  
    > [!NOTE]
    >  Чтобы добавить консольное приложение рабочего процесса в существующее решение, откройте это решение в среде [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)], щелкните правой кнопкой мыши решение в окне **обозревателя решений**, выберите команду **Добавить** и выберите пункт **Новый проект...**. Откроется диалоговое окно **Создание проекта**.Продолжайте действия, описанные ранее в этой процедуре.  
  
8.  Шаблон проекта создает определение службы как XAML.[!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] открывает режим конструктора с действием <xref:System.Activities.Statements.Sequence>, которое содержит набор действий <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply>.  
  
## См. также  
 [Как создать действие](../Topic/How%20to:%20Create%20an%20Activity.md)   
 [Создание проекта рабочего процесса](../workflow-designer/creating-a-workflow-project.md)