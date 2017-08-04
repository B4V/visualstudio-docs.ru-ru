---
title: "Пошаговое руководство. Простая привязка данных в проекте уровня документа"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "данные [разработка решений Office в Visual Studio], привязка данных"
  - "привязка данных [разработка решений Office в Visual Studio], ячейки листа к полю базы данных"
  - "поле базы данных [разработка решений Office в Visual Studio]"
  - "простая привязка данных [разработка решений Office в Visual Studio]"
  - "листы [разработка решений Office в Visual Studio], привязка ячейки листа к полю базы данных"
ms.assetid: 6b8fd638-af13-4ea1-b1c0-2763e2d8ae23
caps.latest.revision: 58
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 57
---
# Пошаговое руководство. Простая привязка данных в проекте уровня документа
  В этом пошаговом руководстве демонстрируются основные сведения о привязке данных в проекте уровня документа.  Одно поле данных в базе данных SQL Server привязывается к именованному диапазону в Microsoft Office Excel.  В пошаговом руководстве также показано, как добавлять элементы управления, позволяющие прокручивать все записи в таблице.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 В данном пошаговом руководстве рассмотрены следующие задачи:  
  
-   Создание источника данных для проекта Excel.  
  
-   Добавление элементов управления на лист.  
  
-   Прокручивание записей базы данных.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] или [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Доступ к серверу с примером базы данных "Northwind" SQL Server.  
  
-   Разрешения на чтение из базы данных SQL Server и запись в нее.  
  
## Создание нового проекта  
 На этом шаге создается проект книги Excel.  
  
#### Создание нового проекта  
  
1.  Создайте проект книги Excel с именем **Простая привязка данных** в Visual Basic или C\#.  Убедитесь, что выбрано **Создать новый документ**.  Дополнительные сведения см. в разделе [Практическое руководство. Создание проектов Office в Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Созданная книга Excel открывается в конструкторе Visual Studio. Проект "Простая привязка данных" добавляется в **Обозреватель решений**.  
  
## Создание источника данных  
 Чтобы добавить типизированный набор данных в проект, следует использовать окно **Источники данных**.  
  
#### Создание источника данных  
  
1.  Если окно **Источники данных** не отображается, его отображение в строке меню, выбирая **Вид**, **Другие окна**, **Источники данных**.  
  
2.  Выберите **Добавить новый источник данных**, чтобы запустить **Мастер настройки источника данных**.  
  
3.  Выберите **База данных** и нажмите **Далее**.  
  
4.  Выберите подключение к базе данных SQL Server "Northwind" или добавьте новое подключение с помощью кнопки **Новое подключение**.  
  
5.  После выбора или создания подключения нажмите **Далее**.  
  
6.  Чтобы сохранить подключение, снимите флажок, если он установлен, и нажмите **Далее**.  
  
7.  В окне **Объекты базы данных** разверните узел **Таблицы**.  
  
8.  Установите флажок возле таблицы **Клиенты**.  
  
9. Нажмите кнопку **Готово**.  
  
 Мастер добавит таблицу **Клиенты** в окно **Источники данных**.  Также к проекту добавляется типизированный набор данных, который отображается в **Обозревателе решений**.  
  
## Добавление элементов управления на лист  
 Для выполнения этого пошагового руководства потребуется два именованных диапазона и четыре кнопки на первом листе.  Сначала добавьте два именованных диапазона из окна **Источники данных**, чтобы обеспечить их автоматическое связывание с источником данных.  Далее добавьте кнопки с **Панели элементов**.  
  
#### Добавление двух именованных диапазонов  
  
1.  Убедитесь, что книга **Мои простые данные Binding.xlsx** открыта в конструкторе Visual Studio, и отображается **Лист1**.  
  
2.  Откройте окно **Источники данных** и разверните узел **Клиенты**.  
  
3.  Выберите столбец **Имя компании** и щелкните отображаемую стрелку раскрывающегося списка.  
  
4.  Выберите в раскрывающемся списке объект **NamedRange** и перетащите его в ячейку **A1** столбца **Имя компании**.  
  
     Элемент управления <xref:Microsoft.Office.Tools.Excel.NamedRange> с именем `companyNameNamedRange` is created in cell **A1**.  Одновременно в проект добавляются элемент управления <xref:System.Windows.Forms.BindingSource> с именем `customersBindingSource`, адаптер таблиц и экземпляр класса <xref:System.Data.DataSet>.  Элемент управления связан с объектом <xref:System.Windows.Forms.BindingSource>, который в свою очередь связан с экземпляром <xref:System.Data.DataSet>.  
  
5.  Выберите столбец **Идентификатор клиента** в окне **Источники данных** и затем щелкните по стрелке появившегося раскрывающегося списка.  
  
6.  Выберите в раскрывающемся списке объект **NamedRange** и перетащите его в ячейку **B1** столбца **Идентификатор клиента**.  
  
7.  Элемент управления <xref:Microsoft.Office.Tools.Excel.NamedRange> с именем `customerIDNamedRange` создается в ячейке **B1** и привязывается к <xref:System.Windows.Forms.BindingSource>.  
  
#### Добавление четырех кнопок  
  
1.  Со вкладки **Стандартные элементы управленияПанели элементов** перетащите элемент управления <xref:System.Windows.Forms.Button> в ячейку **A3** листа.  
  
     Этой кнопке присваивается имя `Button1`.  
  
2.  Добавьте еще три кнопки в следующие ячейки по порядку, их имена будут следующими:  
  
    |Ячейка|\(Имя\)|  
    |------------|-------------|  
    |B3|Button2|  
    |C3|Button3|  
    |D3|Button4|  
  
 Далее следует добавить текст для кнопок. В C\# также добавляются обработчики событий.  
  
## Инициализация элементов управления  
 Установите текст кнопки и добавьте обработчики событий в событии <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup>.  
  
#### Инициализация элементов управления  
  
1.  В **Обозревателе решений** щелкните правой кнопкой мыши **Лист1.vb** или **Лист1.cs** и выберите в контекстном меню команду **Перейти к коду**.  
  
2.  В метод `Sheet1_Startup` добавьте следующий код, в котором задается текст каждой кнопки.  
  
     [!code-csharp[Trin_VstcoreDataExcel#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreDataExcel#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#2)]  
  
3.  Добавьте обработчики событий для событий Click кнопок в метод `Sheet1_Startup` \(только для C\#\).  
  
     [!code-csharp[Trin_VstcoreDataExcel#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#3)]  
  
 Добавьте обработчик событий <xref:System.Windows.Forms.Control.Click> кнопок, чтобы пользователь мог просматривать записи прокруткой.  
  
## Добавление кода, включающего прокрутку записей  
 Чтобы включить перемещение по записям, добавьте код в обработчики событий <xref:System.Windows.Forms.Control.Click> для каждой кнопки.  
  
#### Переход к первой записи  
  
1.  Добавьте обработчик событий <xref:System.Windows.Forms.Control.Click> кнопки `Button1` и добавьте следующий код, чтобы перейти к первой записи:  
  
     [!code-csharp[Trin_VstcoreDataExcel#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#4)]
     [!code-vb[Trin_VstcoreDataExcel#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#4)]  
  
#### Переход к предыдущей записи  
  
1.  Добавьте обработчик событий <xref:System.Windows.Forms.Control.Click> кнопки `Button2` и добавьте следующий код, чтобы перейти к записи, находящейся на одну позицию раньше:  
  
     [!code-csharp[Trin_VstcoreDataExcel#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#5)]
     [!code-vb[Trin_VstcoreDataExcel#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#5)]  
  
#### Переход к следующей записи  
  
1.  Добавьте обработчик событий <xref:System.Windows.Forms.Control.Click> кнопки `Button3` и добавьте следующий код, чтобы перейти к записи, находящейся на одну позицию дальше:  
  
     [!code-csharp[Trin_VstcoreDataExcel#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreDataExcel#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#6)]  
  
#### Переход к последней записи  
  
1.  Добавьте обработчик событий <xref:System.Windows.Forms.Control.Click> кнопки `Button4` и добавьте следующий код, чтобы перейти к последней записи:  
  
     [!code-csharp[Trin_VstcoreDataExcel#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreDataExcel#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#7)]  
  
## Тестирование приложения  
 Теперь можно выполнить тестирование книги, чтобы проверить возможность просмотра записей в базе данных при помощи прокрутки.  
  
#### Проверка рабочей книги  
  
1.  Нажмите клавишу F5 для запуска проекта.  
  
2.  Убедитесь, что первая запись появилась в ячейках **A1** и **B1**.  
  
3.  Нажмите кнопку **\>** \(`Button3`\) и убедитесь, что следующая запись появилась в ячейках **A1** и **B1**.  
  
4.  Нажмите на другую прокручивающую кнопку и убедитесь, что записи меняются так, как это предполагалось.  
  
## Следующие действия  
 Данное пошаговое руководство демонстрирует основные понятия привязки именованного диапазона к полю в базе данных.  Далее будут рассмотрены следующие задачи:  
  
-   Кэширование данных для использования в автономном режиме.  Дополнительные сведения см. в разделе [Практическое руководство. Кэширование данных для автономного использования или для использования на сервере](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md).  
  
-   Привязка ячейки к нескольким столбцам в таблице вместо одного поля.  Дополнительные сведения см. в разделе [Пошаговое руководство. Сложная привязка данных в проекте уровня документа](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md).  
  
-   Использование <xref:System.Windows.Forms.BindingNavigator> для прокрутки записи.  Дополнительные сведения см. в разделе [Практическое руководство. Переход между данными с помощью элемента управления BindingNavigator в Windows Forms](http://msdn.microsoft.com/library/0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb).  
  
## См. также  
 [Привязка данных к элементам управления в решениях Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Данные в решениях Office](../vsto/data-in-office-solutions.md)   
 [Пошаговое руководство. Сложная привязка данных в проекте уровня документа](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md)  
  
  