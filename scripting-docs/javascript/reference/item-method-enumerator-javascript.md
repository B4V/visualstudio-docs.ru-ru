---
title: "Метод item (Enumerator) (JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "item"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Item - метод"
ms.assetid: a88e93f2-42df-4578-a4f9-0760bd074185
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# Метод item (Enumerator) (JavaScript)
Возвращает текущий элемент в коллекции.  
  
> [!WARNING]
>  Этот объект поддерживается только в Internet Explorer.  
  
## Синтаксис  
  
```  
  
enumObj.item()  
```  
  
## Заметки  
 Обязательная ссылка *enumObj* представляет собой любой объект `Enumerator`.  
  
 Метод **item** возвращает текущий элемент. Если коллекция пуста или текущий элемент не определен, этот метод возвращает значение **undefined**.  
  
## Пример  
 В следующем коде метод **item** используется для возврата элемента коллекции `Drives`.  
  
```javascript  
function ShowDrives()  
{  
    var s = "";  
    var bytesPerGB = 1024 * 1024 * 1024;  
  
    var fso = new ActiveXObject("Scripting.FileSystemObject");  
    var e = new Enumerator(fso.Drives);  
  
    e.moveFirst();  
    while (e.atEnd() == false)  
    {  
        var drv = e.item();  
  
        s += drv.Path + " - ";  
  
        if (drv.IsReady)  
        {  
            var freeGB = drv.FreeSpace / bytesPerGB;  
            var totalGB = drv.TotalSize / bytesPerGB;  
  
            s += freeGB.toFixed(3) + " GB free of ";  
            s += totalGB.toFixed(3) + " GB";  
        }  
        else  
        {  
            s += "Not Ready";  
        }  
  
        s += "<br />";  
  
        e.moveNext();  
    }  
    return(s);  
}  
```  
  
## Требования  
 Поддерживается в следующих режимах документов: случайный режим, стандартный режим Internet Explorer 6, стандартный режим Internet Explorer 7, стандартный режим Internet Explorer 8, стандартный режим Internet Explorer 9, стандартный режим Internet Explorer 10. Не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)]. См. [Сведения о версии](../../javascript/reference/javascript-version-information.md).  
  
 **Применимо к**: [Объект Enumerator](../../javascript/reference/enumerator-object-javascript.md)  
  
## См. также  
 [Метод atEnd \(Enumerator\)](../../javascript/reference/atend-method-enumerator-javascript.md)   
 [Метод moveFirst \(Enumerator\)](../../javascript/reference/movefirst-method-enumerator-javascript.md)   
 [Метод moveNext \(Enumerator\)](../../javascript/reference/movenext-method-enumerator-javascript.md)