---
title: "Доступность функций по типам приложений Office и проектов"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "надстройки [разработка решений Office в Visual Studio]"
  - "надстройки уровня приложения [разработка решений Office в Visual Studio]"
  - "настройки уровня документа [разработка решений Office в Visual Studio]"
  - "области формы [разработка решений Office в Visual Studio], доступные функции"
  - "Office - приложения [разработка решений Office в Visual Studio], доступные функции"
  - "Office - разработка решений в Visual Studio, функции"
  - "Office - проекты [разработка решений Office в Visual Studio], доступные функции"
  - "лента [разработка решений Office в Visual Studio]"
ms.assetid: 3e9aa4d3-affb-4f76-bc67-49fe5f26a6a1
caps.latest.revision: 53
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 52
---
# Доступность функций по типам приложений Office и проектов
  В Visual Studio есть шаблоны проектов нескольких типов, которые поддерживают различные бизнес\-сценарии для приложений Microsoft Office, включая следующие типы:  
  
-   Настройки на уровне документа.  
  
-   Надстройки VSTO.  
  
 Не все приложения могут использовать любой тип проекта.  Например, проекты уровня документа доступны только для Microsoft Office Word и Microsoft Office Excel.  Аналогичным образом, некоторые функции доступны только для проектов или приложений определенных типов.  Например, панель действий доступна только в проектах уровня документа, а расширения ленты — только для некоторых приложений.  Дополнительные сведения о различных типах проектов см. в статье [Общие сведения о разработке решений Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
> [!NOTE]  
>  Шаблоны проектов Office доступны только в некоторых выпусках [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  Дополнительные сведения см. в статье [Настройка компьютера для разработки решений Office](../vsto/configuring-a-computer-to-develop-office-solutions.md).  
  
## Типы проектов, доступные для различных приложений Microsoft Office  
 В следующей таблице указаны приложения, которые можно использовать в проекте каждого типа.  
  
|Типы проектов|Приложение Microsoft Office|  
|-------------------|---------------------------------|  
|Настройки уровня документа.|Excel<br /><br /> Word|  
|Надстройки VSTO|Excel<br /><br /> InfoPath \(только InfoPath 2013 и InfoPath 2010\).<br /><br /> Outlook \- приложение<br /><br /> PowerPoint<br /><br /> Проект<br /><br /> Visio<br /><br /> Word<br /><br /> Excel|  
  
## Функции, доступные в проектах различного типа  
 В следующей таблице показано, какие функции доступны в каких типах проектов.  
  
|Функция|Типы проектов, предоставляющие функцию|Дополнительные сведения|  
|-------------|--------------------------------------------|-----------------------------|  
|Панель действий.|Проекты уровня документа.|[Общие сведения о панели действий](../vsto/actions-pane-overview.md)|  
|Развертывание ClickOnce.|Проекты VS и уровня документа.|[Развертывание решения Office](../vsto/deploying-an-office-solution.md)|  
|Настраиваемые области задач.|Проекты надстроек VSTO для следующих приложений:<br /><br /> -   Excel<br />-   InfoPath \(только InfoPath 2013 и InfoPath 2010\).<br />-   Outlook \- приложение<br />-   PowerPoint<br />-   Word|[Настраиваемые области задач](../vsto/custom-task-panes.md)|  
|Пользовательские XML\-части.|Проекты уровня документа.<br /><br /> Проекты уровня приложения для следующих приложений:<br /><br /> -   Excel<br />-   PowerPoint<br />-   Word|[Общие сведения о пользовательских XML-частях](../vsto/custom-xml-parts-overview.md)|  
|Кэш данных.|Проекты уровня документа.|[Кэшированные данные в настройках уровня документа](../vsto/cached-data-in-document-level-customizations.md)|  
|Предоставление объекта в надстройке VSTO другим решениям Microsoft Office.|Проекты надстроек VSTO.|[Вызов кода в надстройках VSTO из других решений Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)|  
|Следующие элементы управления ведущего приложения:<br /><br /> -   Диаграмма<br />-   ListObject.<br />-   NamedRange.<br />-   Элементы управления содержимым<br />-   Закладка|Проекты уровня документа.<br /><br /> Проекты надстроек VSTO для Word и Excel.|[Общие сведения о ведущих элементах и элементах управления ведущего приложения](../vsto/host-items-and-host-controls-overview.md)|  
|Следующие элементы управления ведущего приложения:<br /><br /> -   XMLMappedRange.<br />-   XMLNode.<br />-   XMLNodes.|Проекты уровня документа.|[Общие сведения о ведущих элементах и элементах управления ведущего приложения](../vsto/host-items-and-host-controls-overview.md)|  
|Развертывание нескольких проектов.|Проекты уровня документа.<br /><br /> Проекты надстроек VSTO.|[Пошаговое руководство. Развертывание нескольких решений Office с помощью одного установщика ClickOnce](http://msdn.microsoft.com/ru-ru/051223c0-4082-4799-b78b-a4763a9def55)|  
|Области формы Outlook.|Проекты надстроек VSTO для Outlook.|[Создание областей форм Outlook](../vsto/creating-outlook-form-regions.md)|  
|Действия, выполняемые после развертывания.|Проекты уровня документа.<br /><br /> Проекты надстроек VSTO.|[Пошаговое руководство. Копирование документа на компьютер пользователя после установки ClickOnce](http://msdn.microsoft.com/ru-ru/100090f7-bc63-4152-b3e1-19b48bc27466)|  
|Настройки ленты.|Проекты уровня документа.<br /><br /> Проекты надстроек VSTO для следующих приложений:<br /><br /> -   Excel<br />-   InfoPath \(только InfoPath 2013 и InfoPath 2010\).<br />-   Outlook \- приложение<br />-   PowerPoint<br />-   Проект<br />-   Visio<br />-   Word|[Обзор ленты](../vsto/ribbon-overview.md)|  
|Визуальный конструктор документов.|Проекты уровня документа.|[Проекты Office в среде Visual Studio](../vsto/office-projects-in-the-visual-studio-environment.md)|  
  
## См. также  
 [Начало работы &#40;разработка решений Office в Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Общие сведения о разработке решений Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Общие сведения о панели действий](../vsto/actions-pane-overview.md)   
 [Обзор ленты](../vsto/ribbon-overview.md)   
 [Создание областей форм Outlook](../vsto/creating-outlook-form-regions.md)   
 [Общие сведения о ведущих элементах и элементах управления ведущего приложения](../vsto/host-items-and-host-controls-overview.md)   
 [Кэшированные данные в настройках уровня документа](../vsto/cached-data-in-document-level-customizations.md)   
 [Развертывание решения Office](../vsto/deploying-an-office-solution.md)  
  
  