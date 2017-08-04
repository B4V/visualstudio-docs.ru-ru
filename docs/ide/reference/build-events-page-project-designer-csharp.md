---
title: "Страница \"События сборки\" в конструкторе проектов (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cs.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- Project Designer, Build Events page
- pre-build events
- post-build events
ms.assetid: 3fff9ae5-213c-46ea-a660-1d70acb6c922
caps.latest.revision: 16
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
ms.translationtype: HT
ms.sourcegitcommit: 63aad78bdc7df685ca3a73ec16a9cbc87b78151f
ms.openlocfilehash: 56b2566f727c60b2dd516f578d77ff679a02ce62
ms.contentlocale: ru-ru
ms.lasthandoff: 07/14/2017

---
# <a name="build-events-page-project-designer-c"></a>Страница "Событий построения" в конструкторе проектов (C#)
Страница **События сборки** в **конструкторе проектов** позволяет задать инструкции по конфигурации сборки. На ней также можно указать условия, при которых будут выполняться события, следующие после сборки. Дополнительные сведения см. в статьях [Практическое руководство. Указание событий сборки (C#)](../../ide/how-to-specify-build-events-csharp.md) и [Практическое руководство. Указание событий сборки (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Конфигурация**  
 Данный элемент управления нельзя изменить на этой странице. Описание этого элемента управления см. в статье [Страница "Сборка" в конструкторе проектов (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Платформа**  
 Этот элемент управления нельзя изменить на этой странице. Описание этого элемента управления см. в статье [Страница "Сборка" в конструкторе проектов (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Командная строка события перед сборкой**  
 Определяет команды, выполняемые перед началом сборки. Для ввода длинных команд нажмите кнопку **Изменить событие "Перед сборкой"**, чтобы открыть диалоговое окно ["Командная строка события перед сборкой" или "Командная строка события после сборки"](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).  
  
> [!NOTE]
>  События перед сборкой не выполняются, если проект актуален и сборка не запускается.  
  
 **Командная строка события после сборки**  
 Определяет все команды, выполняемые после завершения сборки. Для ввода длинных команд нажмите кнопку **Изменить событие "После сборки"**, чтобы открыть диалоговое окно **"Командная строка события перед сборкой" или "Командная строка события после сборки"**.  
  
> [!NOTE]
>  Добавьте оператор `call` перед всеми командами после сборки, запускающими BAT-файлы. Например, `call C:\MyFile.bat` или `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
 **Выполнить событие после сборки**  
 Определяет следующие условия для выполнения события после сборки, как показано в приведенной ниже таблице.  
  
|Параметр|Результат|  
|------------|------------|  
|**Всегда**|Событие после сборки будет выполняться независимо от успешности сборки.|  
|**При удачной сборке**|Событие после сборки будет выполняться в случае успешной сборки. Событие будет выполняться даже для актуального проекта, если его сборка завершилась успешно.|  
|**При обновлении выходных файлов проекта во время сборки**|Событие после сборки будет выполняться только в том случае, если выходной файл компилятора (EXE или DLL) отличается от предыдущего выходного файла компилятора. Таким образом, событие после сборки не выполняется, если проект актуален.|  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Указание событий сборки (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Практическое руководство. Назначение событий сборки (C#)](../../ide/how-to-specify-build-events-csharp.md)   
 [Справочник по свойствам проектов](../../ide/reference/project-properties-reference.md)   
 [Компилирование и сборка](../../ide/compiling-and-building-in-visual-studio.md)