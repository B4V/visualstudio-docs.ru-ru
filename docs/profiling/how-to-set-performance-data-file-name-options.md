---
title: "Практическое руководство. Настройка параметров имени файла данных профилирования | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d7a8d6b9-ab23-46fb-98ed-774781157860
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# Практическое руководство. Настройка параметров имени файла данных профилирования
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

По умолчанию для сохранения файла данных профилирования \(VSP\) используется следующий синтаксис:  
  
 *Path\\VSP\-File\\YYMMDD\(N\)* **.vsp**  
  
 Любой из параметров именования можно изменить на странице "Общие" диалогового окна свойств сеанса производительности.  
  
 **Требования**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
|||  
|-|-|  
|*Path*|Каталог, содержащий отчет.  Расположение по умолчанию — папка решений или расположение по умолчанию для проектов и решений пользователя.|  
|*VSP\-File*|Имя файла данных профилирования.  Имя по умолчанию — это имя профилируемого решения или исполняемого файла.|  
|*YYMMDD*|Отметка даты, в которой указывается год, месяц и день сбора данных профилирования.|  
|*\(N\)*|При наличии нескольких файлов данных профилирования к имени файла в скобках добавляется возрастающий номер.|  
  
### Изменение синтаксиса именования файлов данных профилирования сеанса анализа производительности  
  
1.  В **Обозревателе производительности** щелкните правой кнопкой мыши имя сеанса анализа производительности и выберите команду **Свойства**.  
  
2.  Щелкните **Общие**.  
  
3.  В группе **Отчет** измените любые из следующих параметров.  
  
    |||  
    |-|-|  
    |**Расположение отчета**|Позволяет задать каталог для хранения файлов данных профилирования.|  
    |**Имя отчета**|Позволяет задать основное имя фалов.|  
    |**Автоматически добавлять новые отчеты к сеансу**|Установите этот флажок для автоматического добавления файла данных в сеанс анализа производительности.|  
    |**Добавлять номер с приращением к созданным отчетам**|Установите этот флажок для добавления возрастающего номера к имени файла при наличии нескольких файлов с одинаковым именем.  Чтобы перезаписать существующий файл, снимите этот флажок.|  
    |**Использовать метку времени для номера**|Установите этот флажок для добавления метки даты к имени файла.|