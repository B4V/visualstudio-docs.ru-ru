---
title: "Определители формата в C# | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "CSharp"
helpviewer_keywords: 
  - "отладчик, распознаваемые описатели формата"
  - "выражения [C#], значения форматирования"
  - "описатели формата, отладчик"
  - "Контрольное значение - диалоговое окно, описатели формата в C#"
  - "Контрольное значение - диалоговое окно, использование описателей формата"
  - "описатели"
  - "описатели, формат переменных в контрольных значениях"
  - "символы, форматирование переменных в контрольных значениях"
  - "переменные [отладчик], символы переменных в контрольных значениях"
  - "символы переменных в контрольных значениях"
  - "Контрольные значения - окно, описатели формата в C#"
ms.assetid: 345c8589-5f36-4d34-a58c-e56271687dd6
caps.latest.revision: 29
caps.handback.revision: 29
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Определители формата в C# #
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

С помощью спецификаторов формата можно изменить формат, в котором значение отображается в окне **Контрольные значения**. Спецификаторы форматов можно также использовать в окне **интерпретации**, окне **команд** и даже в окнах исходного кода. Если вы приостановите выполнение на выражении в одном из этих окон, результат отобразится в подсказке по данным. Отображение результата в подсказке по данным будет соответствовать спецификатору формата.  
  
 Чтобы применить спецификатор формата, введите выражение и запятую. После запятой добавьте соответствующий спецификатор.  
  
## Использование спецификаторов формата  
 Предположим, что имеется следующий код:  
  
```  
{ int my_var1 = 0x0065; int my_var2 = 0x0066; int my_var3 = 0x0067; }  
```  
  
 Добавьте переменную `my_var1` в окно «Контрольные значения» \(во время отладки выберите **Отладка \/ Окна \/ Контрольные значения \/ Контрольные значения 1**\) и задайте шестнадцатеричный вывод \(в окне **Контрольные значения** щелкните переменную правой кнопкой мыши и выберите пункт **Шестнадцатеричный вывод**\). Теперь в окне **Контрольные значения** показано значение 0x0065. Чтобы представить это значение в виде десятичного, а не шестнадцатеричного целого числа, в столбце «Имя» после имени переменной добавьте спецификатор десятичного формата: **, d**. В столбце «Значение» теперь отображается десятичное значение 101.  
  
 ![WatchFormatCSharp](../debugger/media/watchformatcsharp.png "WatchFormatCSharp")  
  
## Спецификаторы формата  
 В следующей таблице показаны спецификаторы формата C\#, распознаваемые отладчиком.  
  
|класса хранения|Формат|Исходное контрольное значение|Отображение|  
|---------------------|------------|-----------------------------------|-----------------|  
|ac|Принудительное вычисление выражения. Это может быть полезно в том случае, когда неявное вычисление свойств и неявные вызовы функций отключены. См. раздел [Побочные эффекты и выражения](../Topic/Side%20Effects%20and%20Expressions.md).|Сообщение «Неявное вычисление функций выключено пользователем»|\<value\>|  
|d|Десятичное целое число|0x0065|101|  
|dynamic|Отображает указанный объект с помощью динамического представления.|Отображает все члены объекта, включая динамическое представление|Отображает только динамическое представление|  
|h|шестнадцатеричное целое число|61541|0x0000F065|  
|nq|строка без кавычек|"Моя строка"|Моя строка|  
|hidden|Отображает все открытые и не являющиеся открытыми члены.|Отображение открытых членов|Отображение всех членов|  
|raw|Отображает элемент в том виде, в котором он отображается в узле необработанного элемента. Допустимо только для прокси\-объектов.|Dictionary\<T\>|Базовое представление Dictionary\<T\>|  
|results|Используется с переменной типа, реализующего интерфейс IEnumerable или IEnumerable\<T\>. Обычно это результат запроса. Отображает только члены, которые содержат результат запроса.|Отображение всех членов.|Отображение членов, соответствующих условиям запроса.|  
  
## См. также  
 [Окна "Контрольные значения" и "Быстрая проверка"](../debugger/watch-and-quickwatch-windows.md)   
 [Окна переменных](../Topic/Variable%20Windows.md)