---
title: 'Практическое: столбцов ListObject карты к данным'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Office development in Visual Studio], mapping to ListObject column
- ListObject control, mapping data
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b77d33b8d30ed7f581e27e1cbe07d0c90715ff04
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "35675135"
---
# <a name="how-to-map-listobject-columns-to-data"></a>Практическое: столбцов ListObject карты к данным
  При привязке элемента управления <xref:Microsoft.Office.Tools.Excel.ListObject> к <xref:System.Data.DataTable>вы можете не захотеть отображать все столбцы в списке или можете иметь некоторые столбцы, не привязанные к данным. Можно указать, какие столбцы должны отображаться в объекте <xref:Microsoft.Office.Tools.Excel.ListObject> , при вызове метода <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> .  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 ![ссылка на видео](../vsto/media/playvideo.gif "ссылка на видео") демонстрационные видеоматериалы см. в разделе [практические советы Создание списка в Excel, подключенного к списку SharePoint?](http://go.microsoft.com/fwlink/?LinkID=130263).  
  
## <a name="map-columns"></a>Сопоставление столбцов  
  
### <a name="to-map-a-data-table-to-columns-in-a-list"></a>Сопоставление таблицы данных со столбцами в списке  
  
1.  Создайте <xref:System.Data.DataTable> на уровне класса.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#16](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#16)]
     [!code-vb[Trin_VstcoreHostControlsExcel#16](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#16)]  
  
2.  Добавьте примеры столбцов и данных в `Startup` обработчик событий `Sheet1` класса (в проекте уровня документа) или `ThisAddIn` класса (в проекте надстройки VSTO).  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#17](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#17)]
     [!code-vb[Trin_VstcoreHostControlsExcel#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#17)]  
  
3.  Вызовите метод <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> и передайте в него имена столбцов в порядке их отображения. Объект-список будет привязан к вновь созданному <xref:System.Data.DataTable>, но порядок столбцов в объекте-списке будет отличаться от порядка их появления в <xref:System.Data.DataTable>.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#18](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#18)]
     [!code-vb[Trin_VstcoreHostControlsExcel#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#18)]  
  
## <a name="specify-unmapped-columns"></a>Укажите несопоставленные столбцы  
 При сопоставлении столбцов с <xref:System.Data.DataTable>можно также указать, что определенные столбцы не должны быть привязаны к данным, передав пустую строку. Затем новый столбец, не привязанный к данным, добавляется в элемент управления <xref:Microsoft.Office.Tools.Excel.ListObject> .  
  
### <a name="to-specify-an-unmapped-column-when-mapping-listobject-columns"></a>Указание несопоставленного столбца при сопоставлении столбцов ListObject  
  
1.  Вызовите метод <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> и передайте в него имена столбцов в порядке их отображения. Используйте пустую строку, чтобы указать, где добавляется несопоставленный столбец; в данном случае такой столбец добавляется между столбцом заголовка столбца и столбцом фамилии.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#19)]
     [!code-vb[Trin_VstcoreHostControlsExcel#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#19)]  
  
## <a name="compile-the-code"></a>Компиляция кода  
 В этом примере кода предполагается, что в листе, в котором этот код появляется, имеется существующий элемент управления <xref:Microsoft.Office.Tools.Excel.ListObject> с именем `list1` .  
  
## <a name="see-also"></a>См. также  
 [Расширение документов Word и книг Excel в надстройках VSTO во время выполнения](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Элементы управления в документах Office](../vsto/controls-on-office-documents.md)   
 [Добавление элементов управления в документы Office во время выполнения](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Практическое: с данными элемент управления ListObject заливки](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [Автоматизация Excel с помощью расширенных объектов](../vsto/automating-excel-by-using-extended-objects.md)   
 [Элемент управления ListObject](../vsto/listobject-control.md)  
  
  