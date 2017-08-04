---
title: "Представление \"Взаимодействия уровня\" | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.view.tierinteraction
helpviewer_keywords:
- Tier Interactions view
ms.assetid: bb4fb21c-f3f7-473a-8b5e-442da4c2c445
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 63aad78bdc7df685ca3a73ec16a9cbc87b78151f
ms.openlocfilehash: 941d4e6d48d1e61804266b0fb334368145986eb1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/14/2017

---
# Представление "Взаимодействие между уровнями"
<a id="tier-interactions-view" class="xliff"></a>
Профилирование уровневого взаимодействия позволяет получить дополнительные сведения о времени выполнения в функциях многоуровневых приложений, взаимодействующих с базой данных посредством [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)]. Данные собираются только для синхронных вызовов функций.  
  
 **Requirements**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)]  
  
 В представлении взаимодействия сведения об уровневом взаимодействии отображаются в двух областях.  
  
-   Главная область представляет собой иерархическое дерево. Строка верхнего уровня содержит статистические данные для подключений страницы или процесса [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] к базе данных. Дочерние узлы содержат статистические данные по подключениям родительского узла к базе данных.  
  
-   Если щелкнуть узел вызова базы данных в главной области, то в области сведений будут показаны сведения об экземпляре вызова базы данных.  
  
 Время отображается в виде числа миллисекунд или числа тактов процессора. Для изменения отображаемой единицы времени откройте меню **Сервис**, выберите пункт **Параметры**, а затем выберите одно из значений параметра **Показывать значения времени как**.  
  
## Главная область
<a id="master-pane" class="xliff"></a>  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Имя**|— Для строки верхнего уровня — имя профилируемого процесса или веб-страницы.<br />— Для строки подключения к базе данных — имя сервера, на котором располагается база данных.|  
|**База данных**|Имя базы данных (только для строк подключения к базе данных).|  
|**Количество**|Общее число запросов, созданных процессом, веб-страницей или подключением к базе данных.|  
|**Общее затраченное время**|Общее количество времени, затраченного на выполнение любого запроса из процесса, веб-страницы или подключения к базе данных.|  
|**Максимальное затраченное время**|Максимальное количество времени, затраченного на выполнение любого запроса из процесса, веб-страницы или подключения базы данных.|  
|**Минимальное затраченное время**|Минимальное количество времени, затраченного на выполнение любого запроса из процесса, веб-страницы или подключения базы данных.|  
|**Среднее затраченное время**|Среднее количество времени, затраченного на выполнение запроса из процесса, веб-страницы или подключения базы данных.|  
  
## Область сведений о подключении к базе данных
<a id="database-connection-details-pane" class="xliff"></a>  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Текст команды**|SQL-запрос в запросе.|  
|**Количество запросов**|Количество запусков запроса.|  
|**Общее затраченное время**|Общее время, затраченное на выполнение экземпляров запроса.|  
|**Максимальное затраченное время**|Максимальное время, затраченное на выполнение любого экземпляра запроса.|  
|**Минимальное затраченное время**|Минимальное время, затраченное на выполнение любого экземпляра запроса.|  
|**Среднее затраченное время**|Среднее время, затраченное на выполнение экземпляра запроса.|