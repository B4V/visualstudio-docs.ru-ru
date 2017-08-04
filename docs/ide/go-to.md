---
title: "Перейти | Документы Майкрософт"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 509b2107-23d1-4fb3-987f-ab99ef45b72e
author: BrianPeek
ms.author: brpeek
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
translationtype: Human Translation
ms.sourcegitcommit: 3b812629bf0f655f39c35a56eb1b3ca9113303a6
ms.openlocfilehash: 8bf6d49b21d128d15f5312fb230d4a8e7a8195af
ms.lasthandoff: 03/01/2017

---

# <a name="go-to"></a>Перейти
Существует множество способов перемещения внутри кода в интегрированной среде разработки Visual Studio с помощью клавиатуры и мыши.

<!-- VERSIONLESS -->
## <a name="go-to-all"></a>Перейти ко всем
Эта функция доступна в Visual Studio 2017 и более поздних версиях.  Она позволяет выполнять переход по коду для поиска определенных фрагментов.  Используя простой унифицированный интерфейс, вы можете выполнять поиск конкретной строки, типа, символа, файла и т. д.

### <a name="how-to-use"></a>Использование
* **Клавиатура**
  * Нажмите **CTRL+,** или **CTRL+T**.  (Обратите внимание, что сочетание клавиш может отличаться в зависимости от выбранного профиля.)
* **Мышь**
  * Выберите **Правка > Перейти > Перейти ко всем**.

По умолчанию в верхней правой части интегрированной среды разработки откроется небольшое окно.

![Перейти ко всем](~/ide/media/gotoall.png)

Здесь можно выполнить следующие задачи.
* Введите текст без префикса для поиска с помощью [значков фильтров](#filtered-searches), выбранных под текстовым полем.
* Введите [префикс](#filtered-searches), за которым следует искомый текст.
* Введите знак вопроса (?), чтобы получить дополнительную справку.
  ![Справка по команде "Перейти ко всем"](~/ide/media/gotoall_help.png)

### <a name="filtered-searches"></a>Отфильтрованные поиски
Чтобы сузить область поиска до определенного типа, можно либо использовать префикс при вводе, либо воспользоваться значками под окном поиска, как показано ниже.

Префикс | Значок | Сочетание клавиш | Описание
:----: | ---- | -------- | ---
#      | ![Значок символа](~/ide/media/gotoall_symbolicon.png) | CTRL+1, Ctrl+S | Поиск совпадающих символов
f      | ![Значок файла](~/ide/media/gotoall_fileicon.png)     | CTRL+1, Ctrl+F | Поиск совпадающих имен файлов
m      | ![Значок члена](~/ide/media/gotoall_membericon.png) | Ctrl+1, Ctrl+M | Поиск совпадающих членов
т      | ![Значок типа](~/ide/media/gotoall_typeicon.png)     | Ctrl+1, Ctrl+T | Поиск совпадающих типов
:      | ![Значок строки](~/ide/media/gotoall_lineicon.png)     | CTRL+G         | Переход к введенному номеру строки

### <a name="search-locations"></a>Расположения для поиска
Чтобы сузить область поиска определенными расположениями, используйте два значка документов.

Значок | Описание
---- | ---
![Текущий документ](~/ide/media/gotoall_currentdocument.png) | Поиск только в текущем документе
![Внешние документы](~/ide/media/gotoall_external.png) | Поиск во внешних документах наряду с документами, находящимися в проекте или решении

### <a name="settings"></a>Параметры
Щелкните значок шестеренки ![Значок шестеренки](~/ide/media/gotoall_gear.png) в правом нижнем углу, чтобы изменить порядок работы этой функции.

Параметр | Описание
------- | ---
Использовать вкладку предварительного просмотра | Немедленное отображение выбранного элемента на вкладке предварительного просмотра в интегрированной среде разработки
Показать сведения    | Отображение в окне сведений о проекте, файле, строке и сводных данных из комментариев к документации
Центрировать окно   | Перемещение этого окна в центр интегрированной среды разработки, а не в правый верхний угол
<!-- END VERSIONLESS -->

## <a name="go-to-definition"></a>Перейти к определению
Переход к источнику типа и открытие результатов в новой вкладке:

Ввод        | Функция 
------------ | ---
**Клавиатура** | Поместите текстовый курсор внутри имени типа, а затем нажмите клавишу **F12**
**Мышь**    | Щелкните правой кнопкой мыши имя типа и выберите команду **Перейти к определению**

## <a name="peek-definition"></a>Показать определение
Просмотр определения типа во всплывающем окне, а не на новой вкладке.

Ввод        | Функция 
------------ | ---
**Клавиатура** | Поместите текстовый курсор внутри имени типа, а затем нажмите сочетание клавиш **ALT+F12**
**Мышь**    | Щелкните правой кнопкой мыши имя типа и выберите команду **Показать определение**

Если вы просматриваете другое определение из всплывающего окна, вы начнете путь иерархической навигации, по которому можно перемещаться с помощью кругов и стрелок, расположенных над всплывающим окном.  Дополнительные сведения см. в статье [Практическое руководство. Просмотр и изменение кода с помощью окна "Показать определение" (ALT+F12)](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md).

## <a name="go-to-implementation"></a>Перейти к реализации
Переход от базового класса или типа к его реализациям.  Если существует несколько реализаций, они появятся в окне **Результаты поиска символа**.

Ввод        | Функция 
------------ | ---
**Клавиатура** | Поместите текстовый курсор внутри имени типа, а затем нажмите сочетание клавиш **CTRL+F12**
**Мышь**    | Щелкните правой кнопкой мыши имя типа и выберите команду **Перейти к реализации**

## <a name="find-all-references"></a>Найти все ссылки
Поиск всех мест, где используется метод, свойство или переменная.  Этот параметр можно использовать для проверки неиспользуемого кода и возможных побочных эффектов крупного рефакторинга.  Для перехода между результатами нажимайте клавишу **F8**.

Ввод        | Функция 
------------ | ---
**Клавиатура** | Поместите текстовый курсор внутри имени типа, а затем нажмите сочетание клавиш **CTRL+K, R**
**Мышь**    | Щелкните правой кнопкой мыши имя типа и выберите команду **Найти все ссылки**

## <a name="navigating-results"></a>Переход по результатам
При использовании функций навигации Visual Studio можно перемещаться вперед и назад по стеку.

Ввод        | Функция 
------------ | ---
**CTRL+-**          | Переход назад по стеку
**CTRL+SHIFT+-**    | Переход вперед по стеку

Можно также использовать пункты меню **Вид > Переход назад** и **Вид > Переход вперед**.