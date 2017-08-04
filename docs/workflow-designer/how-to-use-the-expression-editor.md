---
title: "Как использовать редактор выражений | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Presentation.View.ExpressionTextBox.UI"
ms.assetid: b5f961dd-6dda-41a9-9cae-0383d479ef3d
caps.latest.revision: 13
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Как использовать редактор выражений
Редактор выражений является элементом управления [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)], который используется во многих действиях рабочего потока в качестве средства их ввода и вычисления.  Редактор выражений предоставляет полноценные возможности редактирования интегрированной среды разработки, включая IntelliSense, выделение цветом, сведения о параметре, подчеркивание некоторых типов ошибок волнистыми линиями, а также другие функции.  Компилятор проверяет выражение после его ввода.  Если выражение является недопустимым, то отображается значок ошибки.  Кроме того, редактор можно открыть как диалоговое окно **Редактор выражений**.  
  
 Выражения являются литералами или кодом [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], привязанным к аргументам или свойствам.  Они содержат элементы значений \(например,  переменные, константы, литералы, свойства\), которые в сочетании с операциями позволяют получить новое значение.  При написании выражения используется синтаксис VB.NET, даже если приложение находится в программе на языке C\#.  Это означает, что регистр символов не учитывается, сравнение производится при помощи одиночного знака равенства \(\= вместо \=\=\), логические операторы записываются как and и or, а не как && и &#124;&#124;, а **Nothing** используется вместо **null**.  Дополнительные сведения о выражениях и операторах в [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] и некоторые примеры см. в разделе [Операторы и выражения в Visual Basic](http://go.microsoft.com/fwlink/?LinkId=186818).  
  
 **Редактор выражений** работает следующим образом.  
  
-   Если редактор выражений не имеет фокуса ввода, то он выглядит как обычный элемент управления TextBlock.  
  
-   Как только редактор выражений получает фокус ввода, то он работает как элемент управления «Редактор выражений».  При переходе фокуса он снова выглядит как обычный элемент TextBlock.  
  
-   Если установить фокус на редактор выражений в повторно размещенном конструкторе рабочих процессов, то он будет работать как элемент TextBlock.  При переходе фокуса в повторно размещенный конструктор рабочих процессов редактор выражений снова будет работать как обычный элемент TextBlock.  
  
> [!NOTE]
>  Технология Intellisense для редактора выражений доступна только в [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)].  Как в [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)], так и в сценариях с повторным размещением компилятор проверяет выражение после ввода, а редактор выражений показывает значок ошибки, если выражение является недопустимым.  
  
### Использование редактора выражений  
  
1.  Откройте в [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)] существующий или создайте новый проект рабочего процесса.  
  
2.  Добавьте к рабочему процессу какое\-нибудь действие, например <xref:System.Activities.Statements.Assign>.  
  
    > [!NOTE]
    >  Многие действия рабочих процессов имеют редакторы выражений.  Выражение TextBlocks также появляется в конструкторе переменных, конструкторе аргументов и конструкторе динамических аргументов.  Действие <xref:System.Activities.Statements.Assign> используется в качестве примера.  
  
3.  Щелкните редактор выражений в конструкторе операций для действия <xref:System.Activities.Statements.Assign>.  
  
     Серые строки в виде водяных знаков **\<Кому\>** и **\<Введите выражение VB\>** — это текстовые строки по умолчанию для редакторов выражений в действии <xref:System.Activities.Statements.Assign>.  
  
4.  Введите выражение.  При вводе строки заключайте ее в кавычки.  Если аргумент выражения привязывается к переменной, то кавычки не ставятся.  
  
     По завершении выберите область вне редактора выражений для перемещения фокуса в другую часть конструктора.  Это приведет к вычислению компилятором выражения, как описано выше.  
  
     Ввести или изменить выражение можно также по нажатию кнопки с многоточием рядом с именем свойства в таблице свойств.  Откроется диалоговое окно **Редактор выражений**.  
  
## См. также  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>