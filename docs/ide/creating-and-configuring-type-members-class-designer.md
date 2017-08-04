---
title: "Создание и настройка членов типов (конструктор классов) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.classdetails.method
- vs.classdetails.property
- vs.classdetails.parameter
- vs.classdetails.event
- vs.classdetails.field
helpviewer_keywords:
- Class Designer [Visual Studio], member creation
- type members, modifying in Class Designer
- parameters [ASP.NET Web Services], adding to methods
- type members, configuring
- type members
- members
- type members, creating
- members, creating
- Class Designer [Visual Studio], type members
- read-only information, displaying
- members, configuring
- methods [Visual Studio], adding parameters
- Class Details window
- Class Details window, member creation
ms.assetid: 42af8738-3738-4ca7-82ff-edf573a68f96
caps.latest.revision: 24
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: 1b2a1479c20814f55d65504a3dd79fc15a544082
ms.contentlocale: ru-ru
ms.lasthandoff: 05/13/2017

---
# <a name="creating-and-configuring-type-members-class-designer"></a>Создание и настройка членов типов (конструктор классов)
Можно добавить эти члены в типы на схеме классов и настроить данные члены в окне **Сведения о классах**:  
  
|**Тип**|**Элементы, которые тип может содержать**|  
|--------------|--------------------------------|  
|Класс|метод, свойство (для C# и Visual Basic), поле, событие (для C# и Visual Basic), конструктор (метод), деструктор (метод), константа|  
|Enum|член|  
|Интерфейс|метод, свойство, событие (для C# и Visual Basic)|  
|Абстрактный класс|метод, свойство (для C# и Visual Basic), поле, событие (для C# и Visual Basic), конструктор (метод), деструктор (метод), константа|  
|Структура (структура в коде C#)|метод, свойство (для C# и Visual Basic), поле, событие (для C# и Visual Basic), конструктор (метод), константа|  
|Делегат|Параметр|  
|Модуль (только в Visual Basic)|метод, свойство, поле, событие, конструктор, константа|  
  
> [!NOTE]
>  Способствуют более лаконичному объявлению свойств, если в методах доступа "get" и "set" свойства не требуется дополнительная логика, определяемая посредством автоматически внедренных свойств (только C#). Чтобы отобразить полную сигнатуру, необходимо в меню **Диаграмма классов** выбрать **Изменить формат членов**, **Показать полную сигнатуру**. Дополнительные сведения об автоматически реализуемых свойствах см. в статье [Автоматически реализуемые свойства](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties).  
  
## <a name="common-tasks"></a>Общие задачи  
  
|Задача|Справочные материалы|  
|----------|------------------------|  
|**Начало работы**. Перед созданием и настройкой членов типа необходимо открыть окно "Сведения о классах".|-   [Открытие окна "Сведения о классах"](../ide/creating-and-configuring-type-members-class-designer.md#OpenClassDetails)<br />-   [Примечания об использовании сведений о классах](../ide/creating-and-configuring-type-members-class-designer.md#ClassDetailsUsageNotes)<br />-   [Отображение информации только для чтения](../ide/creating-and-configuring-type-members-class-designer.md#ReadOnlyInfo)<br />-   [Сочетания клавиш и кнопок мыши в схеме классов и окне "Сведения о классе" (конструктор классов)](../ide/keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer.md)|  
|**Создание и изменение членов типа**. С помощью окна "Сведения о классах" можно создавать новые члены, изменять существующие члены, а также добавлять параметры в метод.|-   [Создание членов](../ide/creating-and-configuring-type-members-class-designer.md#CreateMembers)<br />-   [Изменение членов типа](../ide/creating-and-configuring-type-members-class-designer.md#ModifyTypeMembers)<br />-   [Добавление параметров в методы](../ide/creating-and-configuring-type-members-class-designer.md#AddMethodParams)|  
  
##  <a name="OpenClassDetails"></a>Открытие окна "Сведения о классах"  
 По умолчанию окно "Сведения о классе" открывается автоматически при открытии новой схемы классов (см. статью [Практическое руководство. Добавление схем классов в проекты (конструктор классов))](../ide/how-to-add-class-diagrams-to-projects-class-designer.md). Помимо этого можно открыть окно "Сведения о классе" следующим образом.  
  
#### <a name="to-open-the-class-details-window"></a>Открытие окна "Сведения о классе"  
  
1.  Щелкните любой класс на схеме правой кнопкой мыши для вызова контекстного меню.  
  
2.  В контекстном меню выберите пункт **Окно сведений о классах**.  
  
 - или  
  
-   В меню "Вид" наведите указатель на пункт **Другие окна**, а затем щелкните **Сведения о классах**.  
  
##  <a name="CreateMembers"></a> Создание членов  
 Элемент можно создать с помощью следующих инструментов:  
  
-   Конструктор классов  
  
-   Панель инструментов окна "Сведения о классе"  
  
-   Окно "Сведения о классе"  
  
> [!NOTE]
>  С помощью процедур, описанных в данном подразделе, можно создать конструкторы и деструкторы. Не забывайте, что конструкторы и деструкторы — это специальные типы методов, которые отображаются в секции **Методы** в фигурах схемы классов и в разделе **Методы** таблицы окна "Сведения о классах".  
  
> [!NOTE]
>  Единственная сущность, которую можно добавить к делегату — это параметр. Обратите внимание, что процедура под названием "Создание элемента с помощью панели инструментов окна "Сведения о классе"" не подходит для данного действия.  
  
#### <a name="to-create-a-member-using-class-designer"></a>Создание элемента с помощью конструктора классов  
  
1.  Правой кнопкой мыши щелкните тип, в который нужно добавить член, выберите пункт **Добавить** и нужный тип члена.  
  
     Будет создана и добавлена в тип новая сигнатура элемента. При этом элементу будет присвоено имя по умолчанию, которое можно изменить в **конструкторе классов**, окне **Сведения о классах** или в окне **Свойства**.  
  
2.  Дополнительно укажите другие сведения об элементе, например его тип.  
  
#### <a name="to-create-a-member-using-the-class-details-window-toolbar"></a>Создание элемента с помощью панели инструментов окна "Сведения о классе"  
  
1.  В рабочей области конструирования выберите тип, в который необходимо добавить элемент.  
  
     Тип станет активным и его содержимое отобразится в окне "Сведения о классе".  
  
2.  На панели инструментов в окне "Сведения о классах" щелкните верхний значок и выберите в раскрывающемся списке пункт **Создать \<член>**.  
  
     Курсор переместится в поле **Имя** в строке типа добавляемого члена. Например, если выбрана команда **Создать свойство**, то курсор переместится в новую строку в разделе **Свойства** окна "Сведения о классах".  
  
3.  Введите имя добавляемого элемента и нажмите клавишу ВВОД (или переместите фокус, например, нажав клавишу TAB).  
  
     Будет создана и добавлена в тип новая сигнатура элемента. Теперь член существует в коде и отображается в **конструкторе классов**, окне "Сведения о классах" и в окне "Свойства".  
  
4.  Дополнительно укажите другие сведения об элементе, например его тип.  
  
#### <a name="to-create-a-member-using-the-class-details-window"></a>Создание элемента с помощью окна "Сведения о классе"  
  
1.  В рабочей области конструирования выберите тип, в который необходимо добавить элемент.  
  
     Тип станет активным и его содержимое отобразится в окне "Сведения о классе".  
  
2.  В окне "Сведения о классах" в разделе, содержащем тип добавляемого члена, щелкните **\<добавить член>**. Например, если необходимо добавить поле, щелкните **\<добавить поле>**.  
  
3.  Введите имя добавляемого элемента и нажмите клавишу ВВОД.  
  
     Будет создана и добавлена в тип новая сигнатура элемента. Теперь член существует в коде и отображается в **конструкторе классов**, окне "Сведения о классах" и в окне "Свойства".  
  
4.  Дополнительно укажите другие сведения об элементе, например его тип.  
  
     **Примечание**. Для создания членов также можно использовать сочетания клавиш. Дополнительные сведения см. в разделе [Сочетания клавиш и кнопок мыши в схеме классов и окне "Сведения о классе" (конструктор классов)](../ide/keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer.md).  
  
##  <a name="ModifyTypeMembers"></a> Изменение членов типа  
 Конструктор классов позволяет изменять члены типов, отображаемые на схеме. Можно изменить члены любого типа, которые отображаются на схеме классов и не являются доступными только для чтения. (См. статью [Отображение информации только для чтения (конструктор классов)](http://msdn.microsoft.com/en-us/33e2d3a9-1668-4d10-ae56-fa09b3156e0a).) Изменить члены типа можно с помощью редактирования прямо на рабочей области конструирования, а также с помощью окна свойств и окна подробного представления класса.  
  
 Все члены, отображаемые в окне подробного представления класса, представляют члены типов на схеме классов. Существует четыре типа членов: методы, свойства, поля и события.  
  
 Все строки члена отображаются под заголовками, которые группируют члены по типу. Например, все свойства отображаются под заголовком **Свойства**, который можно свернуть или развернуть как узел в таблице.  
  
 Каждая строка члена отображает следующие элементы:  
  
-   **Значок члена**  
  
     Каждый тип члена представлен своим значком. Наведите указатель мыши на значок члена, чтобы отобразить сигнатуру члена. Щелкните значок члена или пробел слева от значка члена, чтобы выбрать строку.  
  
-   **Имя члена**  
  
     Столбец **Имя** в строке члена отображает имя члена. Это имя также отображается в свойстве **Имя** окна "Свойства". Данную ячейку можно использовать для изменения имени любого члена с разрешениями на чтение и запись.  
  
     При наведении указателя мыши на имя члена отображается полное имя, если столбец **Имя** слишком узкий, чтобы показать полное имя.  
  
-   **Тип члена**  
  
     Ячейка **MemberType** используется технологией IntelliSense, которая позволяет выбирать тип из списка всех доступных типов в текущем проекте или в проектах, на которые имеются ссылки.  
  
-   **Модификатор члена**  
  
     Измените модификатор видимости члена на `Public` (`public`), `Private` (`private`), `Friend` (`internal`) `Protected` (`protected`), `Protected``Friend` (`protected``internal`) или `Default`.  
  
-   **\<добавить член>**  
  
     Последняя строка в окне "Сведения о классах" содержит текст **\<добавить член>** в ячейке **Имя**. Если выбрана данная ячейка, то можно создать новый член. Дополнительные сведения см. в разделе [Создание членов](../ide/creating-and-configuring-type-members-class-designer.md#CreateMembers).  
  
-   **Свойства члена в окне "Свойства"**  
  
     Окно "Сведения о классе" отображает подмножество свойств члена, которые отображаются в окне "Свойства". Изменение значения свойства в одном месте изменяет значение свойства глобально. Это касается отображения его значения в других местах.  
  
-   **Сводка**  
  
     Ячейка **Сводка** содержит сводную информацию о члене. Щелкните многоточие в ячейке **Сводка**, чтобы просмотреть или изменить сведения в полях **Сводка**, **Тип возвращаемого значения** и **Примечания** для члена.  
  
-   **Скрыть**  
  
     Если установлен флажок **Скрыть**, член в типе отображаться не будет.  
  
#### <a name="to-modify-a-type-member"></a>Изменение члена типа  
  
1.  Выберите тип в конструкторе классов.  
  
2.  Если окно "Сведения о классах" не отображается, нажмите кнопку **Окно сведений о классах** на панели инструментов конструктора классов.  
  
3.  Измените значения в полях сетки окна "Сведения о классе". После каждого изменения нажимайте клавишу ВВОД или перемещайте фокус от измененного поля (например, нажимая клавишу TAB). Изменения немедленно отражаются в коде.  
  
    > [!NOTE]
    >  Если необходимо изменить только имя члена, это можно сделать с помощью редактирования прямо на схеме.  
  
##  <a name="AddMethodParams"></a> Добавление параметров в методы  
 Добавить параметры в методы можно с помощью окна подробного представления класса. Параметры можно настроить так, чтобы они были обязательными или необязательными. Если предоставить значение для свойства **Дополнительное значение по умолчанию** параметра, конструктор сформирует код как необязательный параметр.  
  
 Строки параметров содержат следующие элементы:  
  
-   **Имя**  
  
     Столбец **Имя** в строке параметра отображает имя параметра. Это имя также отображается в свойстве **Имя** окна "Свойства". Данную ячейку можно использовать для изменения имени любого параметра с разрешениями на чтение и запись.  
  
     Если столбец **Имя** слишком узкий, чтобы показать полное имя, необходимо навести указатель мыши на имя параметра.  
  
-   **Тип**  
  
     Ячейка **Тип параметра** используется технологией Intellisense, которая позволяет выбирать тип из списка всех типов, доступных в текущем проекте или в проектах, на которые имеются ссылки.  
  
-   **Модификатор**  
  
     Ячейка **Модификатор** в строке параметра принимает и отображает новый модификатор параметра. Чтобы ввести новый модификатор параметра, используйте раскрывающийся список для выбора из значений **None**, **ref**, **out** или **params** в C# и значений **ByVal**, **ByRef** или **ParamArray** в VB.  
  
-   **Сводка**  
  
     Ячейка **Сводка** в строке параметра позволяет ввести комментарии к коду, отображаемые в IntelliSense при вводе параметра в редактор кода.  
  
-   **\<добавить параметр>**  
  
     Строка последнего параметра члена содержит текст **<add parameter>** в ячейке **Имя**. Щелчок на данной ячейке позволяет создать новый параметр. Дополнительные сведения см. в разделе [Добавление параметра в метод](../ide/creating-and-configuring-type-members-class-designer.md#HowToAddParameterToMethod).  
  
 **Свойства параметра в окне "Свойства"**  
  
 В окне свойств отображаются те же свойства параметра, которые отображаются в окне подробного представления класса: **Имя**, **Тип**, **Модификатор**, **Сводка**, а также свойство **Дополнительное значение по умолчанию**. Изменение свойства в одном месте обновляет значение свойства глобально, включая отображение его значения в других местах.  
  
> [!NOTE]
>  Инструкции по добавлению параметра в делегат см. в разделе [Создание членов](../ide/creating-and-configuring-type-members-class-designer.md#CreateMembers).  
  
> [!NOTE]
>  Несмотря на то что деструктор является методом, у него не может быть параметров.  
  
###  <a name="HowToAddParameterToMethod"></a> Добавление параметра в метод  
  
1.  В области диаграммы щелкните тип, содержащий метод, в который необходимо добавить параметр.  
  
     Тип получит фокус и его содержимое будет отображено в окне "Сведения о классе".  
  
2.  В окне "Сведения о классе" разверните строку метода, в который необходимо добавить параметр.  
  
     Отобразится строка соответствующего параметра, содержащая пару круглых скобок и слова **\<добавить параметр>**.  
  
3.  Щелкните **\<добавить параметр>**, введите имя нового параметра и нажмите клавишу **ВВОД**.  
  
     Новый параметр добавлен в метод и в код метода. Он отображается в окне "Сведения о классе" и в окне "Свойства".  
  
4.  Дополнительно можно указать другие сведения о параметре, например его тип.  
  
### <a name="to-add-an-optional-parameter-to-a-method"></a>Добавление необязательного параметра в метод  
  
1.  На поверхности схемы щелкните тип, содержащий метод, в который необходимо добавить необязательный параметр.  
  
     Тип получит фокус и его содержимое будет отображено в окне "Сведения о классе".  
  
2.  В окне подробного представления класса разверните строку метода, в который необходимо добавить необязательный параметр.  
  
     Отобразится строка соответствующего параметра, содержащая пару круглых скобок и слова **\<добавить параметр>**.  
  
3.  Щелкните **\<добавить параметр>**, введите имя нового параметра и нажмите клавишу **ВВОД**.  
  
     Новый параметр добавлен в метод и в код метода. Он отображается в окне "Сведения о классе" и в окне "Свойства".  
  
4.  В окне свойств введите значение свойства **Дополнительное значение по умолчанию**. После настройки свойства "Дополнительное значение по умолчанию" параметра этот параметр станет необязательным.  
  
    > [!NOTE]
    >  Необязательные параметры должны находиться в конце списка параметров.  
  
##  <a name="ClassDetailsUsageNotes"></a> Примечания об использовании сведений о классах  
 Обратите внимание на следующие советы по работе с окном "Сведения о классе".  
  
 **Изменяемые и неизменяемые ячейки**  
  
 Все ячейки в окне "Сведения о классе" являются изменяемыми за немногими исключениями:  
  
-   Весь тип доступен только для чтения в случаях, когда, например, тип находится в сборке, на которую существует ссылка (см. раздел [Отображение информации только для чтения](http://msdn.microsoft.com/en-us/33e2d3a9-1668-4d10-ae56-fa09b3156e0a)). При выборе фигуры в конструкторе классов окно "Сведения о классе" отображает сведения о типе в состоянии только для чтения.  
  
-   Для индексаторов имя доступно только для чтения, а остальные параметры (тип, модификатор, общие сведения) являются изменяемыми.  
  
-   Параметры всех универсальных шаблонов в окне "Сведения о классе" доступны только для чтения. Чтобы изменить параметр универсального шаблона, необходимо отредактировать его исходный код.  
  
-   Имя параметра типа, которое определено в универсальном типе, доступно только для чтения.  
  
-   Если код типа является нечитаемым (нераспознанным), окно "Сведения о классе" отображает содержимое типа как доступное только для чтения.  
  
 **Окно "Сведения о классах" и исходный код**  
  
-   Чтобы просмотреть исходный код, необходимо щелкнуть правой кнопкой мыши в окне "Сведения о классе" (или конструкторе классов) и затем выбрать пункт "Просмотр кода". Откроется файл исходного кода и будет отображено место выбранного элемента.  
  
-   Изменение исходного кода сразу отражается в сведениях о сигнатуре в конструкторе классов и в окне "Сведения о классе". Если окно "Сведения о классе" закрыто, то обновленные сведения отобразятся при следующем открытии окна.  
  
-   Если код типа является нечитаемым (нераспознанным), окно "Сведения о классе" отображает содержимое типа как доступное только для чтения.  
  
 **Функциональные возможности буфера обмена в окне "Сведения о классах"**  
  
 Из окна "Сведения о классе" можно копировать или вырезать поля или строки и вставлять их в другой тип. Вырезать строку можно только в том случае, если она доступна не только для чтения. При вставке строки окно "Сведения о классе" присваивает строке новое имя (производное от имени копируемой строки) для предотвращения конфликта.  
  
##  <a name="ReadOnlyInfo"></a> Отображение информации только для чтения  
 Конструктор классов и окно "Сведения о классе" могут отображать типы (и члены типов) для следующих элементов:  
  
-   проекта, который содержит схему классов;  
  
-   проекта, на который имеются ссылки из проекта, содержащего схему классов;  
  
-   сборки, на которую имеется ссылка из проекта, содержащего схему классов.  
  
 В двух последних случаях упоминаемая сущность (тип или член) доступна только для чтения в схеме классов, отображающей ее.  
  
 Весь проект или его часть, например отдельные файлы, могут быть доступны только для чтения. В наиболее распространенных случаях проект или один из его файлов доступны только для чтения, если проект находится под контролем системы управления версиями (и не извлечен), если проект существует во внешней сборке или если операционная система задает для файлов проекта права только на чтение.  
  
 **Система управления версиями**  
  
 Поскольку схема классов сохраняется как файл в проекте, то для сохранения всех изменений, выполненных в конструкторе классов или окне "Сведения о классе", необходимо извлекать проект.  
  
 **Проекты, доступные только для чтения**  
  
 Проект может быть доступен только для чтения не только по причине того, что он находится под влиянием системы управления версиями файлов. При закрытии проект отображает диалоговое окно, в котором спрашивается, нужно ли переписать файл проекта, отменить изменения (не сохранять) или не закрывать проект. Если выбрать вариант "переписать", файлы проекта будут перезаписаны и станут доступными для чтения и записи. Будет добавлен новый файл схемы классов.  
  
 **Типы, доступные только для чтения**  
  
 При попытке сохранить проект, содержащий типы, у которых файлы исходного кода доступны только для чтения, откроется диалоговое окно **Сохранение файла, доступного только для чтения**, которое позволяет выбрать либо сохранение файла под новым именем или в новом месте, либо перезапись файла, доступного только для чтения. Если переписать файл, новая копия уже не будет доступной только для чтения.  
  
 Если файл кода содержит синтаксическую ошибку, фигура отображает код, файл которого будет временно доступен только для чтения до устранения синтаксической ошибки. Фигуры в данном состоянии отображают красный текст и красный значок, который отображает подсказку "Файл исходного кода содержит ошибку разбора".  
  
 Ссылочный тип (например, тип .NET Framework), который существует в другом узле проекта или в узле сборки, на которую имеется ссылка, отображается на рабочей области конструирования как доступный только для чтения. Локальный тип, который существует в открытом проекте, доступен для чтения и записи, и его фигура отображается на рабочей области конструирования.  
  
 Индексаторы доступны для чтения и записи в коде и в окне "Сведения о классе", однако имя индексатора доступно только для чтения.  
  
 С помощью конструктора классов или окна "Сведения о классе" невозможно изменить разделяемые методы, поэтому для их изменения необходимо использовать редактор кода.  
  
 С помощью конструктора классов или окна "Сведения о классе" невозможно изменить машинный код C++, поэтому для его изменения необходимо использовать редактор кода.  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Просмотр типов и отношений (конструктор классов)](../ide/viewing-types-and-relationships-class-designer.md)|В диаграмме классов можно отобразить существующие типы, члены и отношения.|  
|[Рефакторинг классов и типов (конструктор классов)](../ide/refactoring-classes-and-types-class-designer.md)|С помощью рефакторинга можно с легкостью изменять имена типов и членов типа. Также можно перемещать члены из одного класса в другой, разделять классы на частичные классы и внедрять интерфейсы.|