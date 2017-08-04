---
title: "Справочные материалы по управляемому коду (разработка решений Office в Visual Studio)"
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
  - "справочные материалы [разработка решений Office в Visual Studio], система Microsoft Office 2007"
  - "разработка решений Office в Visual Studio, справочные материалы"
ms.assetid: 1fa66da0-9d90-4524-ba4f-4da13aab73b5
caps.latest.revision: 22
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 18
---
# Справочные материалы по управляемому коду (разработка решений Office в Visual Studio)
  В этом разделе содержится справочная документация по API для пространств имен и типов, используемых в проектах Office, предназначенных для [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] или [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Справочную документацию по пространствам имен и типам API, используемым в проектах Office, которые предназначены для платформы .NET Framework 3.5, см. в следующем справочном разделе документации по Visual Studio: [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=160658](http://go.microsoft.com/fwlink/?LinkId=160658).  
  
## Содержание  
 <xref:Microsoft.Office.Tools>  
 Содержит классы, общие для программирования решений Office. К ним относятся базовый класс для надстроек VSTO, классы для создания настраиваемых областей задач в настройках VSTO, классы для создания смарт\-тегов в решениях Word и Excel и классы для создания панелей действий в настройках уровня документа.  
  
 <xref:Microsoft.Office.Tools.Excel>  
 Содержит элементы управления ведущего приложения и ведущие элементы, которые могут использоваться в решениях для Excel.  
  
 <xref:Microsoft.Office.Tools.Excel.Controls>  
 Содержит элементы управления Excel и элементы управления Windows Forms, которые могут использоваться в решениях для Excel.  
  
 <xref:Microsoft.Office.Tools.Outlook>  
 Содержит классы, используемые надстройками VSTO для Outlook, включая классы, используемые для создания настраиваемых областей формы.  
  
 <xref:Microsoft.Office.Tools.Ribbon>  
 Содержит классы, используемые для программного изменения настроек ленты, созданных с помощью конструктора лент.  
  
 <xref:Microsoft.Office.Tools.Word>  
 Содержит элементы управления ведущего приложения и ведущие элементы, которые могут использоваться в решениях для Word.  
  
 <xref:Microsoft.Office.Tools.Word.Controls>  
 Содержит элементы управления Word и элементы управления Windows Forms, которые могут использоваться в решениях для Word.  
  
 <xref:Microsoft.VisualStudio.Tools.Applications>  
 Содержит класс <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> и набор связанных классов кэшированных данных. Эти классы могут использоваться для изменения некоторых аспектов настроек уровня документа на компьютерах, на которых не установлен Microsoft Office.  
  
 <xref:Microsoft.VisualStudio.Tools.Applications.Deployment>  
 Содержит интерфейс <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> \(который можно реализовать для создания *действий, выполняемых после развертывания*, для решения Office\), исключения, которые могут возникать при установке решения Office, и другие API, которые являются частью инфраструктуры Visual Studio.  
  
 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime>  
 Содержит основные исключения, которые могут создаваться [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], несколько классов, которые могут использоваться для кэширования данных в настройках уровня документа, и другие API, являющиеся частью инфраструктуры Visual Studio.  
  
 <xref:Microsoft.VisualStudio.Tools.Office.BuildTasks>  
 Содержит классы задач MSBuild, которые используются для сборки проектов Office.  
  
## См. также  
 [Общие сведения об инструментах Visual Studio для среды выполнения Office](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Начало работы &#40;разработка решений Office в Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Образцы и пошаговые руководства разработки Office](../vsto/office-development-samples-and-walkthroughs.md)   
 [Проектирование и создание решений Office](../vsto/designing-and-creating-office-solutions.md)  
  
  