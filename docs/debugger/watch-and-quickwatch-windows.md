---
title: "Окна &quot;Контрольные значения&quot; и &quot;Быстрая проверка&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.watch"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
helpviewer_keywords: 
  - "отладка [Visual Studio], окно контрольных значений"
  - "выражения [отладчик], вычисление"
  - "переменные [отладчик], вычисление"
  - "вычисление выражений"
  - "регистры, вычисление"
  - "отладка [Visual Studio], вычисление выражений"
ms.assetid: d5c18377-2a0e-4819-a645-407e24ccc58c
caps.latest.revision: 45
caps.handback.revision: 44
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Окна &quot;Контрольные значения&quot; и &quot;Быстрая проверка&quot;
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Окна **Контрольные значения** \(**Отладка \> Окна \> Контрольные значения \> Контрольные значения \(1, 2, 3, 4\)**\) и **Быстрая проверка** \(**Отладка \> Быстрая проверка**\) можно использовать для наблюдения за переменными и выражениями во время сеанса отладки. Отличие в том, что в окне **Контрольные значения** могут одновременно выводиться несколько переменных, а в окне **Быстрая проверка** — только одна.  
  
## Наблюдение за одной переменной с помощью окна "Быстрая проверка"  
 Окно **Быстрая проверка** можно использовать для наблюдения за одной переменной. Например, предположим, что имеется следующий код:  
  
```c#  
static void Main(string[] args) { int a, b; a = 1; b = 2; for (int i = 0; i < 10; i++) { a = a + b; } }  
```  
  
 Наблюдать за переменной в окне "Быстрая проверка" можно описанным ниже образом.  
  
1.  Установите точку останова на строке `a = a + b;`.  
  
2.  Приступите к отладке. Выполнение прекратится в точке останова.  
  
3.  Откройте окно **Быстрая проверка** \(щелкните переменную правой кнопкой мыши и выберите пункт **Отладка \> Быстрая проверка** или нажмите клавиши **SHIFT\+F9**\). Вы можете открыть окно и добавить переменную в окно **Выражение**, а затем щелкнуть **Пересчитать**. В окне **Значения** должна появиться переменная со значением 2.  
  
4.  **Быстрая проверка** — это модальное диалоговое окно, поэтому вы не можете продолжать отладку, пока оно открыто. Чтобы добавить переменную в окно **Контрольные значения**, можно щелкнуть **Добавить контрольное значение**.  
  
5.  Закройте окно **Быстрая проверка**. Теперь вы можете продолжать отладку, наблюдая за значением в окне **Контрольные значения**.  
  
## Наблюдение за переменными в окне "Контрольные значения"  
 С помощью окна **Контрольные значения** можно наблюдать за несколькими переменными. Например, предположим, что имеется следующий код:  
  
```c#  
static void Main(string[] args) { int a, b, c; a = 1; b = 2; c = 0; for (int i = 0; i < 10; i++) { a++; b *= 2; c = a + b; } }  
  
```  
  
 Добавьте значения трех переменных в окно "Контрольные значения", выполнив указанные ниже действия.  
  
1.  Установите точку останова на строке `c = a + b;`.  
  
2.  Начните отладку \(**F5**\). Выполнение прекратится в точке останова.  
  
3.  Откройте окно "Контрольные значения" \(выберите пункт **Отладка \> Окна \> Контрольные значения \> Контрольные значения 1** или нажмите клавиши **CTRL\+ALT\+W, 1**\).  
  
4.  Добавьте переменную `a` в первую строку, переменную `b` — во вторую строку, а переменную `c` — в третью строку.  
  
5.  Продолжайте отладку.  
  
 В процессе итерации по циклу `for` значения переменных должны меняться.  
  
 При программировании в машинных кодах иногда может потребоваться уточнить контекст имени переменной или выражения, содержащего имя переменной. Контекст — это функция, файл исходного кода и модуль, где находится переменная. Для этого можно использовать синтаксис оператора контекста. Более подробную информацию см. в статье "Выражения в C\+\+".  
  
## Наблюдение за выражениями в окне "Контрольные значения"  
 Теперь попробуем использовать выражение. Добавить можно любое допустимое выражение, которое распознает отладчик.  
  
 Например, если имеется код, приведенный в предыдущем разделе, можно вычислить среднее трех значений следующим образом:  
  
 ![WatchExpression](~/debugger/media/watchexpression.png "WatchExpression")  
  
 В целом правила вычисления выражений в окне **Контрольные значения** аналогичны правилам вычисления выражений в используемом языке программирования. Если в выражении есть синтаксическая ошибка, должна произойти та же ошибка компилятора, которая возникла бы в редакторе кода. Ниже приведен пример.  
  
 ![WatchExpressionError](~/debugger/media/watchexpressionerror.png "WatchExpressionError")  
  
##  <a name="bkmk_refreshWatch"></a> Обновление устаревших контрольных значений  
 В некоторых случаях при вычислении выражения в окне **Контрольные значения** может появиться значок обновления \(кружок с двумя стрелками или двумя волнистыми линиями\).  Например, это может произойти, если вычисление свойств выключено \(**Сервис \> Параметры \> Отладка \> Включить вычисление свойств и другие неявные вызовы функций**\) и имеется следующий код:  
  
```c#  
static void Main(string[] args) { List<string> list = new List<string>(); list.Add("hello"); list.Add("goodbye"); }  
  
```  
  
 Если вы устанавливаете наблюдение за свойством `Count` списка, то должны увидеть что\-то подобное:  
  
 ![RefreshWatch](../debugger/media/refreshwatch.png "RefreshWatch")  
  
 Это указывает на ошибочные или устаревшие значения. Обычно можно обновить значение, щелкнув значок, но в некоторых случаях может быть предпочтительнее не делать этого. Сначала нужно узнать, почему значение не было рассчитано.  
  
 При наведении указателя мыши на значок отображается всплывающая подсказка, в которой указаны причины, по которым нельзя вычислить значение выражения. Значок с изогнутыми стрелками может отображаться по следующим причинам:  
  
-   •	При вычислении выражения возникла ошибка. Например, истекло время ожидания или переменная находилась вне области действия.  
  
-   •	Выражение содержит вызов функции, который мог вызвать побочный эффект в приложении \(см. раздел [Побочные эффекты и выражения](#bkmk_sideEffects)\).  
  
-   Автоматическое вычисление свойств и неявных вызовов функций отладчиком отключено \(**Сервис \> Параметры \> Отладка \> Включить вычисление свойств и другие неявные вызовы функций**\), поэтому выражение нельзя вычислить автоматически.  
  
 Чтобы обновить значение, щелкните значок обновления или нажмите клавишу ПРОБЕЛ. Отладчик попытается пересчитать выражение. Если значок обновления отображался из\-за отключения автоматического вычисления свойств и неявных побочных эффектов, выражение можно вычислить.  
  
 Если появляется значок в виде кружка с двумя волнистыми линиями, выражение не было вычислено из\-за возможной зависимости между потоками. Иными словами, для вычисления коду требуется временно запустить другие потоки в приложении. Как правило, при нахождении в режиме приостановки выполнения все потоки в приложении остановлены. Разрешение временного запуска других потоков может привести к непредвиденным результатам, а также привести к тому, что отладчик будет игнорировать различные события, например точки останова и исключения, созданные в этих потоках.  
  
##  <a name="bkmk_sideEffects"></a> Побочные эффекты и выражения  
 Вычисление некоторых выражений может привести к изменению значения некоторой переменной или иным образом повлиять на состояние программы. Например, вычисление следующего выражения изменяет значение `var1`:  
  
```  
var1 = var2  
```  
  
 Это называется [побочным эффектом](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\)). Побочные эффекты могут усложнить отладку из\-за изменения способа работы программы.  
  
 Если известно, что у выражения есть побочные эффекты, то оно вычисляется только один раз при первом его вводе. Последующие вычисления не выполняются. Этот режим можно отменить, щелкнув значок обновления, который стоит рядом со значением.  
  
 Один из способов избежать любых побочных эффектов — отключить автоматическое вычисление функций \(**Сервис \> Параметры \> Отладка \> Включить вычисление свойств и другие неявные вызовы функций**\).  
  
 Если вычисление свойств и неявных вызовов функций отключено, можно принудительно вычислить выражение с помощью модификатора формата **ac** \(только в C\#\). См. раздел [Определители формата в C\#](../debugger/format-specifiers-in-csharp.md).  
  
## Использование идентификаторов объектов в окне "Контрольные значения" \(C\# и Visual Basic\)  
 Иногда необходимо наблюдать за поведением определенного объекта. Например, может потребоваться отслеживать объект, на который ссылается локальная переменная, после того как эта переменная вышла из области действия. В C\# и Visual Basic можно создавать идентификаторы объектов для определенных экземпляров ссылочных типов и использовать их в окне "Контрольные значения" и условиях точек останова. Идентификатор объекта создается службами отладки среды CLR и связан с объектом.  
  
> [!NOTE]
>  Идентификаторы объектов создают слабые ссылки и не предотвращают сборку мусора для объекта. Они действительны только в рамках текущего сеанса отладки.  
  
 В приведенном ниже коде один метод создает `Person` с помощью локальной переменной, но вам нужно узнать имя `Person` в другом методе.  
  
```c#  
class Person { public Person(string name) { Name = name; } public string Name { get; set; } } public class Program { List<Person> _people = new List<Person>(); public static void Main(string[] args) { MakePerson(); DoSomething(); } private static void MakePerson() { var p = new Person("Bob"); _people.Add(p); } private static void DoSomething() { // more processing Console.WriteLine("done"); } }  
  
```  
  
 Вы можете добавить ссылку на этот объект `Person` в окно **Контрольные значения**, выполнив указанные ниже действия.  
  
1.  Установите точку останова в коде после создания объекта.  
  
2.  Начните отладку и, когда выполнение остановится в точке останова, найдите переменную в окне **Локальные**, щелкните ее правой кнопкой мыши и выберите пункт **Создать идентификатор объекта**.  
  
3.  В окне **Локальные** вы должны увидеть символ **$** и число. Это и есть идентификатор объекта.  
  
4.  Добавьте идентификатор объекта в окно "Контрольные значения".  
  
5.  Установите точку останова там, где нужно отследить поведение объекта.  В приведенном выше коде это место находится внутри метода `DoSomething()`.  
  
6.  Продолжайте отладку и, когда выполнение остановится в методе `DoSomething()`, в окне **Контрольные значения** отобразится объект `Person`.  
  
> [!NOTE]
>  Если необходимо просмотреть свойства объекта, например `Person.Name` в приведенном выше примере, должно быть включено вычисление свойств.  
  
## Использование регистров в окне "Контрольные значения" \(только C\+\+\)  
 При отладке машинного кода, кроме имен переменных, можно добавлять имена регистров с помощью  **$\<имя регистра\>** или **@\<имя регистра\>**.  Для получения дополнительной информации см. [Псевдопеременные](../debugger/pseudovariables.md).  
  
## Динамическое представление и окно "Контрольные значения"  
 В некоторых скриптовых языках \(например, в JavaScript и Python\) используется динамическая или [утиная типизация](https://en.wikipedia.org/wiki/Duck_typing), а в языках .NET \(в версии 4.0 и более поздних\) поддерживаются объекты, за которыми трудно наблюдать с помощью обычных окон отладки, так как у них могут быть свойства и методы времени выполнения, которые нельзя отобразить.  
  
 Когда в окне "Контрольные значения" отображается объект, созданный на основе типа, реализующего [IDynamicMetaObjectProvider Интерфейс](../Topic/IDynamicMetaObjectProvider%20Interface.md), отладчик добавляет специальный узел **Динамическое представление** в окно **Видимые**. В этом узле показаны динамические члены динамического объекта, но не разрешено изменять их значения.  
  
 Если щелкнуть правой кнопкой мыши любой дочерний объект узла **Динамическое представление** и выбрать пункт **Добавить контрольное значение**, отладчик вставит новую контрольную переменную, которая приводит объект к динамическому объекту. Иными словами, **object Name** становится \(**\(dynamic\)object\).Name**.  
  
 Вычисление членов **динамического представления** может иметь побочные эффекты. Объяснение того, что такое побочные эффекты, см. в разделе [Побочные эффекты и выражения](#bkmk_sideEffects). Для C\# отладчик автоматически не пересчитывает значения, отображаемые в **Динамическом представлении** при переходе на новую строку кода. В Visual Basic выражения, добавляемые с помощью **динамического представления**, автоматически обновляются.  
  
 Инструкции по обновлению значений динамического представления см. в разделе [Обновление устаревших контрольных значений](#bkmk_refreshWatch).  
  
 Если нужно отобразить только **динамическое представление** объекта, можно использовать описатель формата **dynamic**.  
  
-   C\#: **ИмяОбъекта, dynamic**  
  
-   Visual Basic: **$dynamic, ИмяОбъекта**  
  
 **Динамическое представление** также улучшает процесс отладки для COM\-объектов. Когда отладчик встречает COM\-объект, инкапсулированный в **System.\_\_ComObject**, он добавляет узел **Динамическое представление** для объекта.  
  
## См. также  
 [Окна отладчика](../debugger/debugger-windows.md)