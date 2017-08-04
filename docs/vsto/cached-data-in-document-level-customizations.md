---
title: "Кэшированные данные в настройках уровня документа"
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
  - "кэширование данных [разработка решений Office в Visual Studio], сведения о кэшировании данных"
  - "данные [разработка решений Office в Visual Studio], кэш"
  - "данные [разработка решений Office в Visual Studio], решения уровня документа"
  - "кэширование данных [разработка решений Office в Visual Studio], сведения о кэшировании данных"
  - "острова данных [разработка решений Office в Visual Studio]"
  - "настройки уровня документа [разработка решений Office в Visual Studio], модель данных"
  - "представление [разработка решений Office в Visual Studio]"
ms.assetid: 84808462-2c5d-4dc8-ab69-491d492b4a51
caps.latest.revision: 27
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 26
---
# Кэшированные данные в настройках уровня документа
  Основной целью настройки уровня документа является отделение данных от представления в документах Office.  Данные ссылаются на сохраненную в документе информацию, включая числа и текст.  Представление ссылается на пользовательский интерфейс, а также на объектную модель Microsoft Office Word и Microsoft Office Excel.  
  
 Visual Studio отделяет данные от представления в настройках уровня документа, позволяя включить данные в качестве *области данных*, также называемой *кэш данных*.  Чтение и изменение данных можно производить непосредственно без запуска Word или Excel.  Это удобно при изменении данных в документах на сервере, на котором не установлены приложения Microsoft Office.  Приложения Word или Excel предназначены для использования в клиентских средах, они не предназначены для выполнения на сервере.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Дополнительные сведения о настройках на уровне документа см. в разделах [Общие сведения о разработке решений Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md) и [Архитектура настроек на уровне документа](../vsto/architecture-of-document-level-customizations.md).  
  
## Основные сведения о модели программирования кэшированных данных  
 Область данных может содержать любой объект решения, отвечающий определенным требованиям.  Сюда входят объекты <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, а также любые другие объекты, которые могут быть сериализованы классом <xref:System.Xml.Serialization.XmlSerializer>.  Дополнительные сведения см. в разделе [Кэширование данных](../vsto/caching-data.md).  
  
 Для представления кэшированных данных можно создать привязку элементов управления Windows Forms и *элементов управления ведущего приложения* в документе с объектами области данных.  Привязка данных между областью данных и элементами управления способствует их синхронизации.  Также можно добавить к данным код проверки, не зависящий от элементов управления.  Дополнительные сведения см. в разделе [Привязка данных к элементам управления в решениях Office](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 Элементы управления являются расширенными версиями собственных объектов в объектной модели Word и Excel.  В отличие от собственных объектов, элементы управления могут быть привязаны непосредственно к объектам управляемых данных.  Дополнительные сведения см. в разделах [Общие сведения о ведущих элементах и элементах управления ведущего приложения](../vsto/host-items-and-host-controls-overview.md) и [Общие сведения об использовании элементов управления Windows Forms в документах Office](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
## Доступ к кэшированным данным на сервере  
 Для доступа к кэшированным данным в документе может использоваться класс <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument>.  Данный класс является частью среды [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] и может быть использован на сервере без запуска приложений Excel или Word.  Когда пользователь открывает документ после того, как были внесены изменения в кэшированные данные, элементы управления, привязанные к данным, автоматически синхронизируются в соответствии с этими изменениями, и пользователю представляются обновленные данные.  Дополнительные сведения см. в разделе [Доступ к данным в документах на сервере](../vsto/accessing-data-in-documents-on-the-server.md).  
  
 Приложениям Excel и Word не требуется выполнять запись в данные на сервере, необходимо только просмотреть их в клиенте.  Более того, не требуется установка приложений Excel и Word на сервере.  Это способствует оптимизации масштабируемости и выполнению быстрой пакетной обработки документов, содержащих области данных.  
  
## Кэширование данных для автономной работы  
 Сохранение данных в области данных дает возможность выполнять сценарии в автономном режиме.  Когда пользователь открывает документ или запрашивает документ с сервера, область данных заполняется самыми последними данными.  Область данных кэшируется в документе и затем становится доступной в автономном режиме.  Пользователь \(и код\) может управлять данными даже без подключения.  После повторного подключения изменения в данных могут быть переданы в источник данных на сервере.  
  
## Сравнение кэшированных данных и пользовательских XML\-частей  
 Пользовательские XML\-части были введены в систему Microsoft Office 2007 для хранения произвольных фрагментов XML в документе.  Несмотря на то что пользовательские XML\-части пригодны для многих скриптов, подобных кэшу данных, существуют некоторые различия между областью данных и пользовательскими XML\-частями.  Дополнительные сведения о настраиваемых XML\-частях см. в разделе [Общие сведения о пользовательских XML-частях](../vsto/custom-xml-parts-overview.md).  
  
 В следующей таблице перечислены некоторые сходные и различные параметры.  
  
||Кэш данных|Пользовательские XML\-части|  
|-|----------------|---------------------------------|  
|Используемые приложения Office.|Настройки уровня документа для следующих приложений:<br /><br /> -   Excel<br />-   Word|Решения уровня документа и уровня приложения для следующих приложений:<br /><br /> -   Excel<br />-   PowerPoint<br />-   Word|  
|Тип данных для хранения.|Открытый объект в сборке настройки, отвечающий определенным требованиям.  Дополнительные сведения см. в разделе [Кэширование данных](../vsto/caching-data.md).|XML\-данные.|  
|Возможность доступа к данным без запуска приложений Microsoft Office.|Да, с использованием класса <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument>, предоставленного средой [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].|Да, с использованием классов в пространстве имен <xref:System.IO.Packaging> или с использованием пакета SDK формата Open XML.|  
  
## См. также  
 [Данные в решениях Office](../vsto/data-in-office-solutions.md)   
 [Архитектура решений Office в Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md)  
  
  