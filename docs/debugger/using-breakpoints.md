---
title: "Использование точек останова | Microsoft Docs"
ms.custom: ""
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "hero-article"
f1_keywords: 
  - "vs.debug.breakpointswin"
  - "vs.debug.disassembly.insert"
  - "vs.debug.sourcewin.edit"
  - "vs.debug.file"
  - "vs.debug.breakpt.new"
  - "vs.debug.whenbreakpointishit"
  - "vs.debug.breakpt.choose"
  - "vs.debug.breakpt.location.address"
  - "vs.debug.breakpt.constraints"
  - "vs.debug.breakpoints.delete"
  - "vs.debug.breakpt.location.data"
  - "vc.breakpoints"
  - "vs.debug.breakpt.condition"
  - "vs.debug.breakpt.location.function"
  - "vs.debug.breakpoints"
  - "vs.debug.menu.insert"
  - "vs.debug.filenames"
  - "vs.debug.breakpt.action"
  - "vs.debug.sourcewin.insert"
  - "vs.debug.address"
  - "vs.debug.data"
  - "vs.debug.func"
  - "vs.debug.breakpt.location.file"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
helpviewer_keywords: 
  - "точки останова, сведения о точках останова"
ms.assetid: 020b2e97-3b3e-4b2c-872d-b5c6025e120e
caps.latest.revision: 57
caps.handback.revision: 56
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Использование точек останова
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Если необходимо остановить выполнение отладчика, например, чтобы увидеть состояние переменных кода или просмотреть стек вызовов, можно установить точки останова. Точка останова — один из важнейших инструментов разработчика для выполнения отладки.  
  
##  <a name="BKMK_Overview"></a> Задание точки останова в функции в исходном коде  
 Можно установить точку останова функции в исходном коде, щелкнув в левом поле файла исходного кода или поместив курсор на строку кода и нажав клавишу F9. Точка останова отображается в виде красной точки в левом поле. Строка кода также окрашивается цветом:  
  
 ![Задание точки останова](~/debugger/media/basicbreakpoint.png "BasicBreakpoint")  
  
 При выполнении этого кода в отладчике выполнение останавливается при достижении точки останова перед выполнением кода в этой строке. Строка исходного кода имеет желтый цвет:  
  
 ![Выполнение точки останова остановлено](~/debugger/media/breakpointexecution.png "BreakpointExecution")  
  
 На этом этапе значение `testInt` равно 1.  
  
 Можно просмотреть текущее состояние приложения, включая значения переменных и стека вызова. Более подробную информацию о стеке вызовов см. в разделе [Практическое руководство. Использование окна стека вызова](../debugger/how-to-use-the-call-stack-window.md).  
  
 Можно установить точку останова в любой строке исполняемого кода. Например, в коде C\# выше можно установить точку останова для объявления переменной, цикла `for` или  всего кода внутри цикла `for`, но нельзя задать точку останова для объявления пространства имен или класса или сигнатуры метода.  
  
##  <a name="BKMK_Set_a_breakpoint_in_a_source_file"></a> Установка других видов точек останова  
 Также можно установить точки останова в стеке вызовов, в окне дизассемблирования и в машинном коде C\+\+ в условии данных или адресе памяти.  
  
## Задание точки останова в окне стека вызовов  
 Можно прервать выполнение на инструкции или строке, к которой возвращается вызывающая функция, установив соответствующую точку останова в окне **Стек вызовов**. Более подробную информацию о стеке вызовов см. в разделе [Практическое руководство. Использование окна стека вызова](../debugger/how-to-use-the-call-stack-window.md). Отладчик должен был остановить выполнение.  
  
1.  Начните отладку приложения и ожидайте остановки выполнения, например в точке останова. Откройте окно **Стек вызовов** \(выберите **Отладка \> Окна \> Стек вызовов** или нажмите клавиши **CTRL\+ALT\+C**\).  
  
2.  Щелкните правой кнопкой мыши вызывающую функцию, затем выберите **Точка останова \/ Вставить точку останова**, или просто нажмите клавишу **F9**.  
  
3.  В левом поле рядом с именем вызова функции появится символ точки останова.  
  
 В окне **Точки останова** точка останова стека вызова будет представлена как адрес с областью памяти, который  соответствует следующей исполняемой инструкции в функции. Отладчик приостанавливает выполнение на этой инструкции.  
  
 Визуальное отслеживание точек останова во время выполнения кода описано в разделе [Сопоставление методов в визуализации стека вызовов при отладке](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md).  
  
## Задание точки останова в окне дизассемблирования  
 Чтобы установить точку останова на инструкции ассемблера, отладчик должен находиться в режиме приостановки выполнения.  
  
1.  Начните отладку приложения и ожидайте остановки выполнения, например в точке останова. Откройте окно **Дизассемблирование** \(выберите **Отладка \> Окна \> Дизассемблирование** или нажмите клавиши **CTRL\+ALT\+D**\).  
  
2.  Щелкните в левом поле инструкцию, на которой необходимо прервать выполнение, или установите курсор в инструкции и нажмите клавишу **F9**.  
  
## Установка точки останова по данным \(только для машинного кода C\+\+\)  
 Точки останова по данным приостанавливают выполнение, когда изменяется указанный адрес памяти. Если значение только считывается, но не изменяется, выполнение программы не прерывается. Чтобы установить точку останова для данных, отладчик должен находиться в режиме приостановки выполнения.  
  
1.  Начните отладку приложения и подождите, пока не будет достигнута точка останова. В меню **Отладка** выберите пункт **Новая точка останова \/ Точка останова по данным** \(или откройте окно **Точки останова** и выберите **Создать \/ Точка останова по данным**.  
  
2.  В поле **Адрес** введите адрес памяти или выражение, результатом вычисления которого будет адрес памяти. Например, для прерывания при изменении содержимого переменной `avar` введите `&avar`.  
  
3.  В раскрывающемся списке **Счетчик байтов** введите количество байтов, за которыми должен наблюдать отладчик. Например, если выбрать **4**, отладчик будет наблюдать за четырьмя байтами начиная с `&avar` и выполнит прерывание, если какой\-либо из этих байтов изменит значение.  
  
 Имейте в виду, что точки останова по данным зависят от применимости определенных адресов памяти.  
  
-   Адреса переменных меняются в разных сеансах отладки. Точки останова по данным автоматически отключаются в конце каждого сеанса отладки.  
  
-   Если установить точку останова по данным на локальную переменную, точка останова остается включенной при завершении выполнения функции, но адрес памяти больше не применяется и поведение точки останова будет непредсказуемым. Если установить точку останова по данным на локальную переменную, рекомендуется удалить или отключить точку останова до окончания функции.  
  
 Точки останова в данных не работают при следующих условиях:  
  
-   Процесс, для которого не выполняется отладка, производит запись в область памяти  
  
-   Область памяти совместно используется двумя или более процессами  
  
-   Область памяти обновляется в ядре. Например, если память передается в функцию `ReadFile` 32\-разрядной версии Windows, память будет обновляться из режима ядра и отладчик не будет прерывать выполнение по записи в память.  
  
## Задание точки останова по адресу памяти \(только в машинном коде C\+\+\)  
 Вы также можете использовать адрес объекта, чтобы установить точку останова в методе, вызываемом для конкретного экземпляра класса.  Ниже приведен пример:  
  
 Например, если имеется объект типа `my_class` с адресом, вы можете задать точку останова функции в методе с именем  `my_method`, вызываемом из этого экземпляра.  
  
1.  Установите точку останова в каком\-либо месте после создания экземпляра класса.  
  
2.  Найдите адрес экземпляра \(допустим, что это `0xcccccccc`\).  
  
3.  Выберите **Отладка \> Создать точку останова \> Точка останова в функции** \(или нажмите клавиши **ALT\+F9, B**\).  
  
4.  В поле **Имя функции** добавьте следующий текст:  
  
    ```cpp  
    ((my_class *) 0xcccccccc)->my_method  
    ```  
  
##  <a name="BKMK_Specify_advanced_properties_of_a_breakpoint_"></a> Управление точками останова  
 Окно **Точки останова** \(**Отладка \> Окна \> Точки останова** или **CTRL\+ALT\+B**\) можно использовать для просмотра всех точек останова, заданных в решении:  
  
 ![Точки останова &#45; окно](~/debugger/media/breakpointswindow.png "BreakpointsWindow")  
  
 Окно **Точки останова** дает возможность централизованно управлять сразу всеми точками останова, что особенно удобно при работе с программой большого объема или в сложных сценариях отладки, где точки останова имеют принципиально важное значение. Кроме того, если требуется сохранить или предоставить другим пользователям состояние и расположение набора точек останова, функция экспорта точек останова и их импорта доступна только в окне **Точки останова**.  
  
##  <a name="BKMK_Specify_a_breakpoint_condition_using_a_code_expression"></a> Улучшенные точки останова  
  
## Условия точки останова  
 Можно управлять тем, где и когда выполняется точка останова, задавая условия.  
  
1.  Щелкните правой кнопкой мыши точку останова или наведите указатель мыши на точку останова и выберите значок "Параметры".  
  
2.  В контекстном меню выберите **Условия**. Откроется окно **Параметры точки останова**:  
  
 ![Параметры точки останова](../debugger/media/breakpointsettings.png "BreakpointSettings")  
  
 Если установить флажок **Условия**, откроется окно с различными видами условий.  
  
 **Условные выражения.** При выборе условного выражения можно выбрать два условия: **Является true** и **При изменении**. Выберите значение **Является true**, если требуется прервать выполнение при истинности выражения, или значение **При изменении**, если требуется прервать выполнение при изменении значения выражения.  
  
 В следующем примере задается применение точки останова, только если значение `testInt` равно **4**:  
  
 ![Условие для точки останова выполнено](../debugger/media/breakpointconditionistrue.png "BreakpointConditionIsTrue")  
  
 В следующем примере задается применение точки останова, только если значение `testInt` изменено:  
  
 ![Точка останова при изменении](../debugger/media/breakpointwhenchanged.png "BreakpointWhenChanged")  
  
 Поведение поля "При изменении" отличается для различных языков программирования. Если значение **При изменении** выбрано для машинного кода, отладчик не рассматривает первое вычисление условия как изменение, поэтому при первом вычислении выражения точка останова не сработает. Если значение **При изменении** выбрано для управляемого кода, точка останова срабатывает при первом вычислении после выбора условия **При изменении**.  
  
 Если условие точки останова имеет недопустимый синтаксис, появится предупреждающее сообщение. Если указать условие для точки останова с недопустимой семантикой, но допустимым синтаксисом, предупреждающее сообщение появится при достижении точки останова в первый раз. В любом случае, отладчик прерывает выполнение при попадании на недопустимую точку останова. Точка останова пропускается, только если условие допустимо и принимает значение `false`.  
  
 Условие может быть любым допустимым выражением, которое распознает отладчик. Более подробную информацию о допустимых выражениях см. в разделе [Выражения в отладчике](../debugger/expressions-in-the-debugger.md).  
  
## Использование идентификаторов объектов в условиях точек останова \(C\# и F\#\)  
 Бывают случаи, когда необходимо посмотреть поведение конкретного объекта; например, может потребоваться узнать, почему объект был вставлен в коллекцию больше одного раза. В C\# и F\# можно создавать идентификаторы объектов для определенных экземпляров [ссылочных типов](/dotnet/csharp/language-reference/keywords/reference-types) и использовать их в условиях точек останова. Идентификатор объекта создается службами отладки среды CLR и связан с объектом.  Чтобы создать идентификатор объекта, выполните следующее.  
  
1.  Установите точку останова в коде после создания объекта.  
  
2.  Начните отладку и, когда выполнение остановится в точке останова, найдите точку останова в окне **Локальные**, щелкните ее правой кнопкой мыши и выберите пункт **Создать идентификатор объекта**.  
  
     В окне **Локальные** вы должны увидеть символ **$** и число. Это и есть идентификатор объекта.  
  
3.  Добавьте новую точку останова в точке, которую нужно исследовать, например в точке добавления объекта в коллекцию.  
  
4.  Используйте идентификатор объекта в поле "Условное выражение". Например, если есть переменная `item`, ссылающаяся на объект, который должен быть добавлен в коллекцию, задайте  **item \=\= $n**, где **n** — номер идентификатора объекта.  
  
     Выполнение прервется в точке добавления объекта в коллекцию.  
  
 Если позже потребуется удалить идентификатор объекта, щелкните правой кнопкой мыши переменную в окне **Локальные** и выберите пункт **Удалить идентификатор объекта**.  
  
 Обратите внимание, что идентификаторы объектов создают слабые ссылки и не предотвращают сборку мусора для объекта. Они действительны только в рамках текущего сеанса отладки.  
  
## Число попаданий  
 Если есть подозрение, что цикл в коде начинает неправильно вести себя после определенного числа итераций, можно установить точку останова для остановки выполнения после указанного числа попаданий в соответствующую строку кода, вместо того чтобы многократно нажимать клавишу **F5** для достижения нужного уровня итерации.  
  
 В окне **Параметры точки останова** задайте в качестве условия **Количество обращений**. Затем можно указать число итераций. В следующем примере задается выполнение точки останова при каждой итерации:  
  
 ![Число попаданий в точку останова](../debugger/media/breakpointhitcount.png "BreakpointHitCount")  
  
## Фильтр  
 Вы можете ограничить точку останова, сделав ее срабатывание возможным лишь на определенных устройствах или в определенных процессах или потоках.  
  
 В окне **Параметры точки останова** задайте в качестве условия **Фильтр**. Задайте одно или несколько выражений, приведенных ниже.  
  
-   MachineName \= "имя"  
  
-   ProcessId \= значение  
  
-   ProcessName \= "имя"  
  
-   ThreadId \= значение  
  
-   ThreadName \= "имя"  
  
 Значения строк следует заключить в двойные кавычки. Для комбинации условий можно использовать знаки `&` \(И\), `||` \(ИЛИ\), `!` \(НЕ\) и скобки.  
  
##  <a name="BKMK_Print_to_the_Output_window_with_tracepoints"></a> Действия точки останова и точки отслеживания  
 Точка трассировки — это точка останова, которая выводит сообщение в окно вывода. Точка трассировки может играть роль временного оператора трассировки в языке программирования.  
  
 В окне **Параметры точки останова** установите флажок **Действия**. В группе **Действие** выберите пункт **Запись сообщения в окне вывода**. Можно вывести универсальную строку, например **это тест**. Чтобы включить в сообщение значение переменной или выражение, используйте фигурные скобки.  
  
 Чтобы приостановить выполнение при достижении точки трассировки, снимите флажок **Продолжить выполнение**. Если флажок **Продолжить выполнение** установлен, выполнение не останавливается. В обоих случаях выводится сообщение.  
  
 В поле **Сообщение** можно использовать приведенные ниже ключевые слова.  
  
|||  
|-|-|  
|**$ADDRESS**|Текущая инструкция|  
|**$CALLER**|Имя вызывающей функции|  
|**$CALLSTACK**|Стек вызовов|  
|**$FUNCTION**|Имя текущей функции|  
|**$PID**|Идентификатор процесса|  
|**$PNAME**|Имя процесса|  
|**$TID**|Идентификатор потока|  
|**$TNAME**|Имя потока|  
|**$TICK**||  
|**$TNAME**||  
  
##  <a name="BKMK_Set_a_breakpoint_at_a_function_return_in_the_Call_Stack_window"></a> Метки точки останова  
 Метки точек останова используются только в окне **Точки останова**. Они служат для сортировки и фильтрации списка точек останова. Для добавления метки к точке останова выберите строку точки останова, затем в контекстном меню выберите команду **Метка**.  
  
## Экспорт и импорт точек останова  
 Чтобы экспортировать точки останова в XML\-файл, щелкните правой кнопкой мыши на точке останова и выберите **Экспорт**. По умолчанию файл сохраняется в каталоге решения. Чтобы импортировать точки останова, откройте окно **Точки останова** \(**CTRL\+ALT\+B**\) и на панели инструментов щелкните стрелку вправо \(подсказка — **Импорт точек останова из файла**\).  
  
## Устранение неполадок точек останова  
  
### После удаления точки останова она по\-прежнему применяется при запуске отладки  
 Если удалить точку останова во время отладки, в некоторых случаях точка останова может снова применяться при очередном запуске отладки. Чтобы прекратить применение этой точки останова, убедитесь, что все ее экземпляры удалены из окна **Точки останова**.  
  
### Отладчик не может найти правильную версию исходного файла для точки останова  
 Если исходный файл изменился и исходный код больше не соответствует отлаживаемому коду, отладчик может найти исходный файл, который соответствует точке останова, даже если исходный файл существует.  
  
1.  Если требуется, чтобы в Visual Studio отображался исходный код, не соответствующий отлаживаемой версии, выберите **Отладка \/ Параметры и настройки**. На странице **Отладка \/ Общие** снимите флажок **Требовать точного соответствия исходной версии файлов**.  
  
2.  Также можно выполнять привязку точки останова к исходному файлу. Выделите точку останова и в контекстном меню выберите пункт **Условия**. Установите флажок **Разрешить наличие отличий в исходном коде от первоначальной версии** в окне **Параметры точки останова**.  
  
### Точки останова не работают в библиотеке DLL  
 Невозможно установить точку останова в исходном файле, если отладчик не загрузил отладочную информацию для модуля, в котором находится код. Признаком такой ситуации может быть, например, сообщение **Точка останова не будет задана**. На месте точки останова появляется глиф предупреждения о точке останова. Эти глифы предупреждений о точке останова, однако, становятся фактическими точками останова после загрузки кода. Более подробную информацию о загрузке символов см. в разделе [Указание файлов символов \(.pdb\) и файлов с исходным кодом](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
## См. также  
 [Навигация по коду с помощью отладчика](../debugger/navigating-through-code-with-the-debugger.md)