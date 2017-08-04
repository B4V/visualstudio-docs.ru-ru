---
title: "Функция CvWriteFlag | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvmarkers/CvWriteFlagExVA"
  - "cvmarkers/CvWriteFlagExW"
  - "cvmarkers/CvWriteFlagExVW"
  - "cvmarkers/CvWriteFlagExA"
helpviewer_keywords: 
  - "CvWriteFlagExW - метод"
  - "CvWriteFlagExVA - метод"
  - "CvWriteFlagExA - метод"
  - "CvWriteFlagExVW - метод"
ms.assetid: ee9da1e2-7b34-4cba-81e2-215d25d32e4d
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# Функция CvWriteFlag
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Записывает флаг в файл трассировки визуализатора параллелизма.  
  
## Синтаксис  
  
```  
HRESULT CvWriteFlagExW(  
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,  
    _In_ CV_IMPORTANCE level,  
    _In_ int category,  
    _In_ PCWSTR pMessage,  
    ...  
    );  
  
HRESULT CvWriteFlagExA(  
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,  
    _In_ CV_IMPORTANCE level,  
    _In_ int category,  
    _In_ PCSTR pMessage,  
    ...  
    );  
  
HRESULT CvWriteFlagExVW(  
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,  
    _In_ CV_IMPORTANCE level,  
    _In_ int category,  
    _In_ PCWSTR pMessage,  
    _In_ va_list argList);  
  
HRESULT CvWriteFlagExVA(  
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,  
    _In_ CV_IMPORTANCE level,  
    _In_ int category,  
    _In_ PCSTR pMessage,  
    _In_ va_list argList);  
```  
  
#### Параметры  
 `argList`  
 Список аргументов.  
  
 `category`  
 Категория.  
  
 `level`  
 Уровень важности.  
  
 `pMarkerSeries`  
 Допустимый контекст метки ряда.  Не может принимать значение NULL.  
  
 `pMessage`  
 Строка форматирования сообщений.  Не может принимать значение NULL.  
  
## Возвращаемое значение  
 S\_ОК, если сообщение успешно записано.  Код ошибки в том случае, если были какие\-либо ошибки.  Используйте макрос SUCCEEDED\/FAILED для проверки условия ошибки.  
  
## Требования  
 **Заголовок:** cvmarkers.h  
  
 **Юникод:** CvWriteFlagExW, CvWriteFlagExVW  
  
 **ANSI:**CvWriteFlagExA, CvWriteFlagExVA  
  
## См. также  
 [Справочник по библиотеке C\+\+](../profiling/cpp-library-reference.md)