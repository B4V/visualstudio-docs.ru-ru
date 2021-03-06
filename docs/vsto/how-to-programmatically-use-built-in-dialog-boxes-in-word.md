---
title: 'Практическое: программное использование встроенных диалоговых окон в Word'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, Word
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f5ee28b0296037b9b5490ca691a27d613c793228
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "35674478"
---
# <a name="how-to-programmatically-use-built-in-dialog-boxes-in-word"></a>Практическое: программное использование встроенных диалоговых окон в Word
  При работе с Microsoft Office Word, бывают случаи, при необходимости отображать диалоговые окна для ввода данных пользователем. Несмотря на то, что вы можете создать свой собственный, можно использовать подход с использованием встроенных диалоговых окон в Word, которые представлены на <xref:Microsoft.Office.Interop.Word.Dialogs> коллекцию <xref:Microsoft.Office.Interop.Word.Application> объекта. Это позволяет получить доступ к более чем 200 встроенных диалоговых окон, которые представлены в виде перечисления.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="display-dialog-boxes"></a>Отображение диалоговых окон  
 Чтобы отобразить диалоговое окно, используйте одно из значений из <xref:Microsoft.Office.Interop.Word.WdWordDialog> перечисления для создания <xref:Microsoft.Office.Interop.Word.Dialog> объект, представляющий окно будет отображаться. Затем вызовите <xref:Microsoft.Office.Interop.Word.Dialog.Show%2A> метод <xref:Microsoft.Office.Interop.Word.Dialog> объекта.  
  
 В следующем примере кода показано, как отобразить **Открытие файла** диалоговое окно. Чтобы использовать этот пример, запустите его из `ThisDocument` или `ThisAddIn` в своем проекте.  
  
 [!code-vb[Trin_VstcoreWordAutomation#100](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#100)]
 [!code-csharp[Trin_VstcoreWordAutomation#100](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#100)]  
  
### <a name="access-dialog-box-members-that-are-available-through-late-binding"></a>Доступа к элементам диалогового окна, доступные через позднее связывание  
 Некоторые свойства и методы диалоговых окон в Word доступны только через позднее связывание. В проектах Visual Basic where **Option Strict** имеет значение on, следует использовать отражение для доступа к этим членам. Дополнительные сведения см. в разделе [позднее связывание в решениях Office](../vsto/late-binding-in-office-solutions.md).  
  
 В следующем примере кода демонстрируется использование **имя** свойство **Открытие файла** диалоговое окно в Visual Basic проецирует where **Option Strict** отключена или в Visual C# проекты, предназначенные [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] или [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Чтобы использовать этот пример, запустите его из `ThisDocument` или `ThisAddIn` в своем проекте.  
  
 [!code-vb[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#122)]
 [!code-csharp[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#122)]  
  
 В следующем примере кода показано, как использовать отражение для доступа к **имя** свойство **Открытие файла** диалоговое окно в Visual Basic проецирует where **Option Strict** — в. Чтобы использовать этот пример, запустите его из `ThisDocument` или `ThisAddIn` в своем проекте.  
  
 [!code-vb[Trin_VstcoreWordAutomation#102](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#102)]  
  
## <a name="see-also"></a>См. также  
 [Практическое: программное использование диалоговых окон Word в скрытом режиме](../vsto/how-to-programmatically-use-word-dialog-boxes-in-hidden-mode.md)   
 [Обзор объектной модели Word](../vsto/word-object-model-overview.md)   
 [Необязательные параметры в решениях Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Оператор Option strict](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [Reflection (C#)](/dotnet/csharp/programming-guide/concepts/reflection) (Отражение (C#))  
 [Reflection (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection) (Отражение (Visual Basic))  
  
  