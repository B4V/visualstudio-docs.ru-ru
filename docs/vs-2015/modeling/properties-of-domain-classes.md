---
title: Свойства доменных классов | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, domain class
ms.assetid: a3993995-19e7-4761-a972-b1de89131a1b
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 3d5ea3d5cad378a476c9080cd56143b1600b7b4d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47561940"
---
# <a name="properties-of-domain-classes"></a>Свойства доменных классов
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [свойства доменных классов](https://docs.microsoft.com/visualstudio/modeling/properties-of-domain-classes).  
  
Доменные классы имеют свойства, в следующей таблице. Сведения о доменных классов, см. в разделе [Общие сведения о моделях, классах и отношениях](../modeling/understanding-models-classes-and-relationships.md). Дополнительные сведения об использовании этих свойств см. в разделе [Настройка и расширение доменного языка](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
|Свойство.|Описание|Значение по умолчанию|  
|--------------|-----------------|-------------|  
|Модификатор доступа|Уровень доступа класса домена (`public` или `internal`).|`public`|  
|Настраиваемые атрибуты|Используется для добавления атрибутов для класса исходного кода, созданный из данного доменного класса.|\<None >|  
|Создает двойной производным|Если `True`, будет создан базовый класс и разделяемый класс (для поддержки настройки посредством переопределений). Дополнительные сведения см. в разделе [переопределение и расширение созданных классов](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Имеет пользовательский конструктор|Если `True`, пользовательский конструктор будет предоставляться в исходном коде. Дополнительные сведения см. в разделе [переопределение и расширение созданных классов](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Модификатор наследования|Описывает тип наследования класса исходного кода, созданный из класса домена (`none`, `abstract` или `sealed`).|`none`|  
|Базовый класс|Если данный доменный класс является производным, имя базового класса.|\<None >|  
|name|Имя данного доменного класса.|Текущее имя|  
|Пространство имен|Пространство имен данного доменного класса.|Текущее пространство имен|  
|Примечания|Неофициальные примечания, связанные с этим доменным классом.|\<None >|  
|Описание|Описание, которое используется для документирования пользовательского интерфейса созданного конструктора.|\<None >|  
|Отображаемое имя|Имя, которое будет отображаться в созданном конструкторе для данного доменного класса.|\<None >|  
|Ключевое слово Help|Необязательное ключевое слово, используемое для индексации справки F1 для данного доменного класса.|\<None >|  
  
## <a name="see-also"></a>См. также  
 [Глоссарий по средствам доменного языка работы](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)


