---
title: "Работа с кодом Visual C++ (конструктор классов) | Документы Майкрософт"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.classdesigner.cpplimitation
helpviewer_keywords:
- Visual C++, Class Designer
- Class Designer, Visual C++ support
- Class Designer, limitations
- Class Designer, tasks in Visual C++
- Visual C++, class diagrams
- C++, class diagrams
- C++, Class Designer
ms.assetid: f5b40921-2ef7-4de0-b595-45b44c79ffa6
caps.latest.revision: 23
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
ms.sourcegitcommit: d2f4eba36e9069a35cf279ccf1c78f72a51d77a1
ms.openlocfilehash: 0d974e9af7d22c5d02b1313cb2e46c873592f4d3
ms.contentlocale: ru-ru
ms.lasthandoff: 06/23/2017

---
# Работа с кодом Visual C++ (конструктор классов)
<a id="working-with-visual-c-code-class-designer" class="xliff"></a>
Конструктор классов отображает визуальную область конструктора, которая называется *схемой классов* и предоставляет визуальное преставление элементов кода в проекте. Схемы классов можно использовать для разработки и визуализации классов и других типов в проекте.  

 Конструктор классов поддерживает следующие элементы кода C++:  

-   Класс (похож на фигуру управляемого класса, за исключением того, что он может иметь несколько отношений наследования)  

-   Анонимный класс (отображает созданное представлением класса имя для анонимного типа)  

-   Класс шаблона  

-   Структура  

-   Enum  

-   Макрос (отображает представление макроса после обработки)  

-   Typedef  

> [!NOTE]
>  Это не аналог схемы классов UML, которую можно создать в проекте моделирования. Дополнительные сведения см. в разделе [UML-схемы классов: справочник](../modeling/uml-class-diagrams-reference.md).  

## Устранение неполадок при разрешении типов и отображение проблем
<a id="troubleshooting-type-resolution-and-display-issues" class="xliff"></a>  

### Расположение исходных файлов
<a id="location-of-source-files" class="xliff"></a>  
 Конструктор классов не отслеживает расположение исходных файлов. Таким образом, при изменении структуры проекта или перемещении исходных файлов в проекте конструктор классов может потерять тип (особенно исходный тип определения типа, базовых классов или типов связи). Может возникнуть ошибка, например **Конструктору классов не удалось отобразить этот тип**. В этом случае перетащите измененный или перемещенный исходный код в схему классов и повторно отобразите ее.  

### Проблемы с обновлением и производительностью
<a id="update-and-performance-issues" class="xliff"></a>  
 Для проектов Visual C++ для отображения изменения в исходном файле на схеме классов может потребоваться от 30 до 60 секунд. Из-за такой задержки конструктор классов может выдать ошибку **В выбранном блоке не найдены типы**. После возникновения подобной ошибки нажмите кнопку **Отмена** в сообщение об ошибке и дождитесь отображения элемента кода в представлении классов. После этого конструктор классов должен быть в состоянии отобразить этот тип.  

 Если схема классов не обновляется для вывода внесенных в код изменений, может потребоваться закрыть схему и снова открыть ее.  

### Проблемы разрешения типа
<a id="type-resolution-issues" class="xliff"></a>  
 Конструктор классов может оказаться не в состоянии разрешить типы по следующим причинам:  
  
-   Тип находится в проекте или сборке, на которые нет ссылок из проекта, содержащего эту схему классов. Чтобы исправить эту ошибку, добавьте ссылку на проект или сборку, содержащие данный тип. Дополнительные сведения см. в статье [Управление ссылками в проекте](managing-references-in-a-project.md).  
  
-   Тип находится в неправильной области действия, поэтому конструктор классов не может его найти. Убедитесь, что в коде присутствует оператор `using`, `imports` или `#include`. Убедитесь также, что этот тип (или связанный тип) не был перемещен из пространства имен, в котором он находился изначально.  

-   Тип не существует (или был закомментирован). Чтобы исправить эту ошибку, убедитесь, что тип не закомментирован и не удален.  

-   Тип находится в библиотеке, на которую ссылается директива #import. В качестве возможного обходного пути можно вручную добавить сформированный код (TLH-файл) в директиву #include в файле заголовка.  

 Для разрешения типов вы с большой вероятностью столкнетесь с ошибкой **Не найдены коды для одной или более фигур в диаграмме классов "\<element>"**. Это сообщение об ошибке не обязательно означает, что код содержит ошибку. Оно указывает лишь на то, что конструктору классов не удалось отобразить код. Попробуйте сделать следующее.  

-   Убедитесь, что тип существует. Убедитесь, что исходный код не был случайно закомментирован или удален.  

-   Убедитесь, что конструктор классов поддерживает введенный вами тип. См. раздел [Ограничения для элементов кода C++](#limitations).  

-   Попытайтесь разрешить тип. Тип может находиться в проекте или сборке, на которые нет ссылок из проекта, содержащего эту схему классов. Чтобы исправить эту ошибку, добавьте ссылку на проект или сборку, содержащие данный тип. Дополнительные сведения см. в статье [Управление ссылками в проекте](../ide/managing-references-in-a-project.md).  

-   Попытайтесь разрешить тип. Тип может находиться в проекте или сборке, на которые нет ссылок из проекта, содержащего эту схему классов. Чтобы исправить эту ошибку, добавьте ссылку на проект или сборку, содержащие данный тип. Дополнительные сведения см. в статье [Управление ссылками в проекте](managing-references-in-a-project.md).  
  
-   Убедитесь, что тип находится в правильной области действия, чтобы конструктор классов мог его найти. Убедитесь, что в коде присутствует оператор `using`, `imports` или `#include`. Убедитесь также, что этот тип (или связанный тип) не был перемещен из пространства имен, в котором он находился изначально.  

### Диагностика других сообщений об ошибках
<a id="troubleshooting-other-error-messages" class="xliff"></a>  
 На открытых форумах Microsoft Developer Network (MSDN) можно получить помощь в устранении ошибок и предупреждений. См. [Форум по конструкторам классов Visual Studio](http://go.microsoft.com/fwlink/?linkid=160754).  

##  <a name="limitations"></a> Ограничения для элементов кода C++  

-   При загрузке проекта Visual C++ конструктор классов работает в режиме только для чтения. Вы можете изменить схему классов, но не можете сохранить изменения из схемы классов обратно в исходный код.  

-   Конструктор классов поддерживает только собственную семантику C++. Для проектов Visual C++, которые компилируются в управляемый код, конструктор классов будет визуализировать только те элементы кода, которые являются собственными типами. Таким образом, вы можете добавить схему классов в проект, но конструктор классов не позволит визуализировать элементы, в которых свойству`IsManaged` назначено значение `true` (то есть типы значений и ссылочные типы).  

-   Для проектов Visual C++ конструктор классов считывает только определение типа. Например, предположим, что вы определяете тип в файле заголовков (H) и определяете его члены в файле реализации (CPP). При выполнении команды "Перейти к схеме классов" для файла реализации (CPP) конструктор класса не отображает ничего. Еще один пример, если вы выполняете команду "Перейти к схеме классов" для CPP-файла, который использует оператор `#include` для включения других файлов, но не содержит фактические определения классов, конструктор класса снова не отображает ничего.  

-   IDL-файлы, которые определяют COM-интерфейсы и библиотеки типов, не отображаются в схемах, пока не будут скомпилированы в машинный код C++.  

-   Конструктор классов не поддерживает глобальные функции и переменные.  

-   Конструктор классов не поддерживает объединения. Это особый тип класса, в котором объем выделяемой памяти равен размеру самого большого элемента данных объединения.  

-   Конструктор классов не отображается базовые типы данных, такие как `int` и `char`.  

-   Конструктор классов не отображает типы, которые определены за пределами текущего проекта, если только проект не содержит правильные ссылки на эти типы.  

-   Конструктор классов может отобразить вложенные типы, но не отношения между вложенным типом и другими типами.  

-   Конструктор классов не может отобразить типы, которые относятся к void или являются производными от типа void.  

## См. также
<a id="see-also" class="xliff"></a>  
 [Разработка и просмотр классов и типов](../ide/designing-and-viewing-classes-and-types.md)   
 [Работа с классами и другими типами (конструктор классов)](../ide/working-with-classes-and-other-types-class-designer.md)   
 [Работа со схемами классов (конструктор классов)](../ide/working-with-class-diagrams-class-designer.md)   
 [Конструирование классов и типов (конструктор классов)](../ide/designing-classes-and-types-class-designer.md)   
 [Дополнительные сведения об ошибках конструктора классов](../ide/additional-information-about-class-designer-errors.md)   
 [Классы Visual C++ в конструкторе классов](../ide/visual-cpp-classes-in-class-designer.md)   
 [Структуры Visual C++ в конструкторе классов](../ide/visual-cpp-structures-in-class-designer.md)   
 [Перечисления Visual C++ в конструкторе классов](../ide/visual-cpp-enumerations-in-class-designer.md)   
 [Операторы typedef языка Visual C++ в конструкторе классов](../ide/visual-cpp-typedefs-in-class-designer.md)
