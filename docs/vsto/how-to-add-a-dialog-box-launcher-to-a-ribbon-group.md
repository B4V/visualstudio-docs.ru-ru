---
title: 'Как: Добавление вызова диалогового окна в группу ленты'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- dialog box launcher [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], dialog box launcher
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2513113b473341f2ed099ef0c5ff5961694acb19
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2018
ms.locfileid: "34548397"
---
# <a name="how-to-add-a-dialog-box-launcher-to-a-ribbon-group"></a>Как: Добавление вызова диалогового окна в группу ленты
  Можно добавить кнопку запуска диалогового окна в любую группу на ленте. Запуска диалогового окна является мелкого значка, который отображается в группе. Пользователь нажимает эту кнопку для открытия диалоговым окнам или панели задач, которые предоставляют дополнительные возможности, относящиеся к группе.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-add-a-dialog-box-launcher-to-a-ribbon-group"></a>Добавление кнопки запуска диалогового окна в группу ленты  
  
1.  Выберите файл кода ленты (*.vb* или *.cs* файл) в **обозревателе решений**.  
  
2.  На **представление** меню, нажмите кнопку **конструктор**.  
  
3.  В конструкторе лент щелкните правой кнопкой мыши любую группу, а затем нажмите кнопку **добавить кнопку вызова диалогового окна**.  
  
     Добавьте код в <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup.DialogLauncherClick> событий группы, чтобы открыть диалоговое окно пользовательских или встроенных.  
  
## <a name="see-also"></a>См. также  
 [Обзор ленты](../vsto/ribbon-overview.md)   
 [Доступ к ленте во время выполнения](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Примеры разработки решений Office и пошаговые руководства](../vsto/office-development-samples-and-walkthroughs.md)   
 [Конструктор лент](../vsto/ribbon-designer.md)   
 [Общие сведения о модели объектов ленты](../vsto/ribbon-object-model-overview.md)   
 [XML-ленты](../vsto/ribbon-xml.md)   
 [Как: экспорт ленты из конструктора лент в XML-ленты](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [Как: изменение положения вкладки на ленте](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)   
 [Как: Настройка встроенной вкладки](../vsto/how-to-customize-a-built-in-tab.md)   
 [Как: Добавление элементов управления в представление backstage](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [Настройка ленты для Outlook](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Как: работа с настройкой ленты](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Как: надстройка Показать ошибки пользовательского интерфейса](../vsto/how-to-show-add-in-user-interface-errors.md)   
 [Пошаговое руководство: Создание настраиваемой вкладки с помощью конструктора лент](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Пошаговое руководство: Обновление элементов управления на ленте во время выполнения](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [Пошаговое руководство: Создание настраиваемой вкладки с помощью XML-ленты](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  