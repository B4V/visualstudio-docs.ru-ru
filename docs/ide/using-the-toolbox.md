---
title: "Использование панели элементов | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.chooseitems
- vs.toolboxpages.activexcontrols
- VS.CHOOSEITEMS.windowsuixamlcomponents
- VS.chooseitems.silverlightcomponents
- VC.EDITORS.RIBBON
- vs.customizetoolbox
- VS.chooseitems.System.Workflow_Components
- vs.chooseitems.frameworkcomponents
- VS.ToolboxPages..NET_Framework_Components
- VS.chooseitems.Microsoft.VisualStudio.Toolbox.VsToolboxPage
- vs.chooseitems.comcomponents
- vs.toolboxpages.NGWS_components
helpviewer_keywords:
- toolbox, adding items
- Visual Studio, toolbox
- toolbox, tabs
- toolbox
ms.assetid: 82e7cb43-4d0b-4e17-b7b0-43f96c22c3c2
caps.latest.revision: 20
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ea9179ad37514ffad4876177b05150eecc22def
ms.openlocfilehash: 8941dd8635b32d9e02ab75256cbe8e2894f762f4
ms.contentlocale: ru-ru
ms.lasthandoff: 05/24/2017

---
# <a name="using-the-toolbox"></a>Использование панели элементов
С помощью панели элементов вы можете добавить в проект элементы управления и другие элементы. Можно перетаскивать различные элементы управления на поверхность используемого конструктора, а также изменять размер и положение элементов управления.  
  
 Панель элементов отображается вместе с представлениями конструктора, например представлением XAML-файла. В панели элементов отображаются только те элементы управления, которые можно использовать в текущем конструкторе.  
  
 Целевая версия .NET Framework проекта также влияет на набор элементов управления, видимых в панели элементов. По умолчанию целевой версией .NET Framework для проектов [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)] является версия 4.5.1. Вы можете выбрать другую целевую версию .NET Framework, выбрав узел проекта в **обозревателе решений** и перейдя к пункту **Свойства/Приложение/Целевая рабочая среда**.  
  
## <a name="managing-the-toolbox-and-its-controls"></a>Управление панелью элементов и элементами управления на ней  
 По умолчанию панель элементов свернута в левой части Visual Studio и отображается при наведении на нее указателя. Вы можете закрепить панель элементов (щелкнув значок **Закрепить** на панели инструментов), чтобы она оставалась открытой всегда. Вы также можете открепить окно панели элементов и переместить его в любое место на экране. Можно закрепить, открепить и скрыть панель элементов, щелкнув правой кнопкой панель инструментов и выбрав один из параметров.  
  
 Вы можете изменить порядок элементов на вкладке панели элементов или добавить пользовательские вкладки, используя следующие команды в контекстном меню.  
  
-   **Переименовать элемент**. Переименование выбранного элемента.  
  
-   **Показать все**. Отображение всех возможных элементов управления (не только тех, которые можно использовать в текущем конструкторе).  
  
-   **Представление списка**. Отображение элементов управления в вертикальном списке. Если этот флажок не установлен, элементы управления размещаются горизонтально.  
  
-   **Выбрать элементы**. Открывает диалоговое окно **Выбор элементов панели элементов**, в котором можно указать элементы, отображаемые на **панели элементов**. Вы можете показать или скрыть элемент, установив или сняв его флажок.  
  
-   **Сортировать элементы по алфавиту**. Сортировка элементов по имени.  
  
-   **Сброс панели**. Восстановление параметров и элементов панели элементов по умолчанию.  
  
-   **Добавить вкладку**. Добавление новой вкладки панели элементов.  
  
-   **Вверх**. Перемещение выбранного элемента вверх.  
  
-   **Вниз**. Перемещение выбранного элемента вниз.  
  
## <a name="creating-and-distributing-custom-toolbox-controls"></a>Создание и распространение настраиваемых элементов управления панели элементов  
 Вы можете создать настраиваемый элемент управления панели элементов на Visual Basic или Visual C#. Проект можно создать на базе шаблона, основанного на [Windows Presentation Foundation](../extensibility/creating-a-wpf-toolbox-control.md) или [Windows Forms](../extensibility/creating-a-windows-forms-toolbox-control.md). Затем можно передать элемент управления коллегам или опубликовать его в Интернете с помощью [установщика элементов управления панели элементов](http://download.microsoft.com/download/8/3/6/836657BD-9CCB-4ED4-B9D2-FB769473B284/TCI_whitepaper.docx).