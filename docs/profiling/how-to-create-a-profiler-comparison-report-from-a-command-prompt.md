---
title: "Практическое руководство. Создание отчета сравнения профилировщиков с помощью командной строки | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00548d16-eb5b-46f7-8a65-862f98a43831
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# Практическое руководство. Создание отчета сравнения профилировщиков с помощью командной строки
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Можно создать отчет средств профилирования [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] о результатах сравнения производительности двух файлов данных профилирования \(VSP или VSPS\).  В отчете отображаются различия, снижение производительности и усовершенствования одного сеанса профилирования по сравнению с другим.  Значения в отчете отражают отклонения или степень изменения по сравнению с базовым планом первого из указанных файлов.  Это отклонение вычисляется на основе разности между старым \(базовым\) значением и результатом нового анализа.  Сравнение данных профилирования может выполняться на основе на функций кода, модулей приложения, строк, указателей инструкций и типов.  
  
 Чтобы перечислить идентификаторы сопоставляемых категорий и полей, используйте следующую командную строку:  
  
 **VSPerfReport \/querydifftables**  *VspFileName1* *VspFileName2*  
  
 Используйте следующий синтаксис URL\-адреса для создания нового рабочего элемента:  
  
 **VSPerfReport \/diff**  `VspFileName1` *VspFileName2* \[**\/**`Options`\]  
  
 В командную строку **VSPerfReport \/diff** можно добавить параметры из следующей таблицы.  
  
|Команда|Описание|  
|-------------|--------------|  
|**DiffThreshold:**\[*Value*\]|Различия между значениями не учитываются, если они ниже заданного порогового значения.  Кроме того, значения ниже данного порога не отображаются.|  
|**DiffTable:** *TableName*|Для сравнения файлов используется указанная таблица.  По умолчанию используется таблица функций.  Укажите идентификатор, содержащийся в списке **VSPerfReport \/querydifftables**.|  
|**DiffColumn:** *ColumnName*|Для сравнения значений используется указанный столбец.  По умолчанию используется столбец, содержащий процентное значение исключительного времени.  Укажите идентификатор, содержащийся в списке **VSPerfReport \/querydifftables**.|