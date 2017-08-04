---
title: "IDiaEnumSegments::get__NewEnum | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaEnumSegments::get__NewEnum - метод"
ms.assetid: 504505fa-b35c-402f-a440-8972c589cc5b
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSegments::get__NewEnum
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Извлекает <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> версия данного перечислителя.  
  
## Синтаксис  
  
```cpp#  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### Параметры  
 pRetVal  
 \[out\] возвращает `IUnknown` интерфейс, представляющий  <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT> версия данного перечислителя.  
  
## Возвращаемое значение  
 В случае успеха возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## См. также  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)