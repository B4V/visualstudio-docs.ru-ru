---
title: 'Практическое: программное создание книг Excel'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel [Office development in Visual Studio], creating workbooks
- workbooks, creating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7e1da9ff331a4376a6ff242dca4382832ee4e85f
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257112"
---
# <a name="how-to-programmatically-create-new-workbooks"></a>Практическое: программное создание книг Excel
  При создании книги программными средствами она является собственным объектом <xref:Microsoft.Office.Interop.Excel.Workbook>, а не ведущим элементом <xref:Microsoft.Office.Tools.Excel.Workbook>.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 В проекте надстройки VSTO можно создать ведущий элемент <xref:Microsoft.Office.Tools.Excel.Workbook> для объекта <xref:Microsoft.Office.Interop.Excel.Workbook>. Дополнительные сведения см. в разделе [документов расширения Word и книг Excel в надстройках VSTO во время выполнения](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="to-create-a-new-workbook"></a>Создание новой книги  
  
1.  Используйте метод <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> коллекции <xref:Microsoft.Office.Interop.Excel.Workbooks>.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#1](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#1)]
     [!code-vb[Trin_VstcoreExcelAutomation#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#1)]  
  
    > [!NOTE]  
    >  Книгу можно создать на основе шаблона, отличного от шаблона по умолчанию: для этого требуемый шаблон следует передать в качестве параметра в метод <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A>.  
  
## <a name="see-also"></a>См. также  
 [Расширение документов Word и книг Excel в надстройках VSTO во время выполнения](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Добавление элементов управления в документы Office во время выполнения](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Работа с книгами](../vsto/working-with-workbooks.md)   
 [Практическое: программное открытие книг Excel](../vsto/how-to-programmatically-open-workbooks.md)   
 [Практическое: программное Сохранение книг Excel](../vsto/how-to-programmatically-save-workbooks.md)   
 [Практическое: программное закрытие книг Excel](../vsto/how-to-programmatically-close-workbooks.md)   
 [Программные ограничения ведущих элементов и элементов управления ведущего приложения](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Необязательные параметры в решениях Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Ведущие элементы и элементы управления](../vsto/host-items-and-host-controls-overview.md)  
  
  