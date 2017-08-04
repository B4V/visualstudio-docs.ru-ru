---
title: "Страница &quot;Параметры&quot;, свойства узла &quot;Текстовый редактор&quot; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tools Options settings, Text Editor node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 19438302-0677-4f4d-9720-5667e6a22ab2
caps.latest.revision: 17
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
translationtype: Human Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 922e6ae930ee146a0e948a659cb128149e140396
ms.lasthandoff: 02/22/2017

---
# <a name="options-page-text-editor-node-properties"></a>Страница "Параметры"", свойства узла "Текстовый редактор"
В этом документе описываются некоторые из страниц (или коллекций свойств) диалогового окна **Параметры**, связанных с категорией **Текстовый редактор** — `DTE.Properties("TextEditor", <Property Page>)`. Заголовок каждого из подразделов представляет собой вызов, используемый для доступа к коллекции `Properties`, а таблицы содержат списки свойств в коллекции.  
  
 Макросы Visual Basic в разделе [Управление параметрами](http://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d) демонстрируют, как отображать текущие параметры и их значения для каждой страницы диалогового окна **Параметры**.  
  
## <a name="general"></a>Общие  
 `DTE.Properties("TextEditor", "General")`  
  
|Имя элемента свойства|Значение|Описание|  
|------------------------|-----------|-----------------|  
|GoToAnchorAfterEscape|Get/Set (Boolean)|Если задано значение `True`, то при нажатии кнопки "escape" во время выделения точка вставки переместится туда, откуда началось выделение. При значении `False` точка вставки переместится в другой конец выделения.|  
|DragNDropTextEditing|Get/Set (Boolean)|Определяет, можно ли перетащить выбранный блок текста из одного места документа в другое для выполнения операций копирования, вставки или вырезания.|  
|HorizontalScrollBar|Get/Set (Boolean)|Определяет, будет ли отображаться горизонтальная полоса прокрутки окна редактора.|  
|VerticalScrollBar|Get/Set (Boolean)|Определяет, будет ли отображаться вертикальная полоса прокрутки окна редактора.|  
|SelectionMargin|Get/Set (Boolean)|Определяет, есть ли место слева от текстовой панели для выполнения специальных операций выбора, отображения значка точки останова и так далее.|  
|MarginIndicatorBar|Get/Set (Boolean)|Определяет, есть ли вертикальная полоса, разделяющая левую сторону текстовой панели от основной ее части.|  
|UndoCaretActions|Get/Set (Boolean)|Если `True`. операции отмены включают перемещение точки вставки, команды выбора и так далее в дополнение к действиям редактирования, меняющим содержимое буфера.|  
|AutoDelimiterHighlighting|Get/Set (Boolean)|Определяет, должен ли редактор выделять открывающий разделитель цветом, когда пользователь вводит соответствующий закрывающий разделитель. Независимо от значения этого свойства, открывающий разделитель всегда выделяется полужирным шрифтом.|  
|EditorEmulation|Get/Set (Enum)||  
|DetectUTF8WithoutSignature|Get/Set (Boolean)|Определяет, используется ли в файле кодировка UTF-8, когда у файла отсутствует сигнатура кодировки.|  
|TrackChanges|Get/Set (Boolean)||  
  
## <a name="plain-text"></a>Обычный текст  
 `DTE.Properties("TextEditor", "PlainText")`  
  
 Параметры редактора `PlainText` влияют на настройки редактора при редактировании текстовых файлов. Для каждого языка программирования и пакета [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] доступны определенные параметры **Текстового редактора**. Например, для просмотра или изменения параметров редактора [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] используйте `DTE.Properties("TextEditor", "CSharp") or DTE.Properties("TextEditor", "CSharp-Specific")`. Для параметров редактора **Скрипт SQL** используйте `DTE.Properties("TextEditor", "SQL ")`.  
  
|Имя элемента свойства|Значение|Описание|  
|------------------------|-----------|-----------------|  
|AutoListMembers|Get/Set (Boolean)|Определяет, должен ли автоматически открываться доступный список членов, когда пользователь вводит точку после ссылки на переменную.|  
|AutoListParams|Get/Set (Boolean)|Определяет, должно ли автоматически отображаться описание списка аргументов, когда пользователь вводит "(" после имени функции.|  
|HideAdvancedMembers|Get/Set (Boolean)|Определяет, должен ли оператор завершения выводить список всех членов или только часто используемых.|  
|VirtualSpace|Get/Set (Boolean)|Определяет, должны ли пробелы отображаться графически. Если этому свойству присвоить значение `true`, то элементу свойства `WordWrap` (в этом списке) будет присвоено значение `false`.|  
|WordWrap|Get/Set (Boolean)|Определяет, будут ли в представлении отображаться длинные строки с переносом на границах слов. Если этому свойству присвоить значение `true`, то элементу свойства `VirtualSpace` (в этом списке) будет присвоено значение `false`.|  
|WordWrapGlyphs|Get/Set (Boolean)|Отображает глиф в конце строки; это указывает, что строка переносится на следующую строку.|  
|EnableLeftClickForURLs|Get/Set (Boolean)|Определяет, должен ли редактор подчеркивать URL-адреса и позволять переходить по данному URL-адресу посредством щелчка левой кнопкой мыши, сделанного в зарегистрированном системном веб-браузере.|  
|IndentStyle|Get/Set (<xref:EnvDTE.vsIndentStyle>)|Определяет стиль отступов.: Default, Smart или None.|  
|TabSize|Get/Set (Long)|Представляет величину шага табуляции в знаках. Не допускается использовать целое число вне диапазона от 1 до 60 (включительно).|  
|InsertTabs|Get/Set (Boolean)|`True` означает использование знаков табуляции в отступах.|  
|IndentSize|Get/Set (Long)|Представляет величину одного уровня отступа в знаках. Не допускается использовать целочисленное значение вне диапазона от 1 до 60 (включительно).|  
|ShowLineNumbers|Get/Set (Boolean)|Определяет, должны ли отображаться номера строк вдоль левого поля.|  
|ShowNavigationBar|Get/Set (Boolean)|Определяет, появляются ли раскрывающиеся списки и кнопки вверху окон редактора.|  
|CutCopyBlankLines|Get/Set (Boolean)|Вырезает или копирует пустые строки при их выборе.|  
  
## <a name="see-also"></a>См. также  
 [Управление параметрами](http://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [Определение имен элементов свойств на страницах параметров](http://msdn.microsoft.com/Library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [Страница "Параметры", свойства узла "Среда"](../../ide/reference/options-page-environment-node-properties.md)   
 [Страница "Параметры", свойства узла "Шрифты и цвета"](../../ide/reference/options-page-fonts-and-colors-node-properties.md)