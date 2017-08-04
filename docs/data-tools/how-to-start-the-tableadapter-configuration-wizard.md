---
title: "Практическое руководство. Запуск мастера настройки адаптера таблицы | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "мастер настройки адаптера таблицы"
  - "адаптеры таблиц TableAdapter, мастер настройки"
ms.assetid: 301f2dcd-ed72-4229-80ef-3b59cb062d5d
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# Практическое руководство. Запуск мастера настройки адаптера таблицы
**Мастер настройки адаптера таблицы** создает и изменяет адаптеры таблицы в строго типизированных базах данных.  Этот мастер создает адаптеры таблицы на основе вводимых вами в мастере инструкций SQL или существующих хранимых процедур в базе данных.  Этот мастер может также создавать новые хранимые процедуры в базе данных на основе инструкций SQL, вводимых вами в мастере.  
  
### Запуск мастера настройки адаптера таблицы для создания нового адаптера таблицы  
  
1.  Откройте свой набор данных в **Конструкторе наборов данных**.  Для получения дополнительной информации см. [Практическое руководство. Открытие набора данных в конструкторе наборов данных](../Topic/How%20to:%20Open%20a%20Dataset%20in%20the%20Dataset%20Designer.md).  
  
    > [!NOTE]
    >  Если в вашем проекте нет набора данных, см. раздел [Практическое руководство. Создание типизированного набора данных](../data-tools/create-and-configure-datasets-in-visual-studio.md).  
  
2.  Если вы создаете новый адаптер таблицы, перетащите объект **Адаптер таблицы** со вкладки **Набор данных Панели элементов** в **Конструктор наборов данных**.  
  
3.  На странице **Выбор подключения базы данных** выберите подключение к данным в списке доступных подключений или выберите **Создать подключение** для создания нового подключения.  
  
### Запуск мастера настройки адаптера таблицы для изменения существующего адаптера таблицы  
  
1.  Откройте свой набор данных в **Конструкторе наборов данных**.  Для получения дополнительной информации см. [Практическое руководство. Открытие набора данных в конструкторе наборов данных](../Topic/How%20to:%20Open%20a%20Dataset%20in%20the%20Dataset%20Designer.md).  
  
2.  Щелкните адаптер таблицы правой кнопкой мыши в **Конструкторе наборов данных** и выберите пункт **Настройка**.  Открывается страница **Создание инструкций SQL** или **Привязка команд к хранимым процедурам** мастера в зависимости от изначальной настройки адаптера таблицы.  
  
3.  Выполните указания мастера.  
  
## См. также  
 [Пошаговые руководства работы с данными](../Topic/Data%20Walkthroughs.md)   
 [Привязка элементов управления Windows Forms к данным в Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Общие сведения об адаптере таблиц](../data-tools/tableadapter-overview.md)   
 [Создание и изменение типизированных наборов данных](../data-tools/creating-and-editing-typed-datasets.md)   
 [Общие сведения об источниках данных](../data-tools/add-new-data-sources.md)   
 [Практическое руководство. Подключение к данным в базе данных](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [Проверка данных](../Topic/Validating%20Data.md)   
 [Практическое руководство. Сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms](../Topic/How%20to:%20Sort%20and%20Filter%20ADO.NET%20Data%20with%20the%20Windows%20Forms%20BindingSource%20Component.md)   
 [Практическое руководство. Создание таблицы подстановок с помощью компонента BindingSource в формах Windows Forms](../Topic/How%20to:%20Create%20a%20Lookup%20Table%20with%20the%20Windows%20Forms%20BindingSource%20Component.md)   
 [Пошаговое руководство. Отображение данных на форме в приложении Windows](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)