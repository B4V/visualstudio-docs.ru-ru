---
title: "Размещение пользовательского элемента управления в окне инструментов | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "окна инструментов, добавление пользовательских элементов управления"
  - "пользовательские элементы управления [пакет SDK для Visual Studio], добавление в окна инструментов"
  - "пользовательские элементы управления [пакет SDK для Visual Studio]"
ms.assetid: 869f3195-e152-4e61-802c-51d6b7ba3e36
caps.latest.revision: 29
caps.handback.revision: 29
manager: "douge"
---
# Размещение пользовательского элемента управления в окне инструментов
В этом пошаговом руководстве показано, как добавить пользовательский элемент управления в окно инструментов.  
  
 Пользовательский элемент управления — это набор элементов управления Windows, объединенных в одном элементе управления. Чтобы добавить пользовательский элемент управления в окно инструментов, все, что на самом деле нужно сделать, — это разместить пользовательский элемент управления на **панели элементов**. В качестве пользовательского элемента управления в этом пошаговом руководстве используется элемент управления "Часы", разработанный в разделе [Пример. Создание составного элемента управления с помощью C\#](../Topic/Walkthrough:%20Authoring%20a%20Composite%20Control%20with%20Visual%20C%23.md).  
  
## Обязательные компоненты  
 Для выполнения этого пошагового руководства необходимо установить пакет SDK для Visual Studio. Для получения дополнительной информации см. [SDK для Visual Studio](../extensibility/visual-studio-sdk.md).  
  
## Создание пользовательского элемента управления  
  
1.  Создайте элемент управления "Часы", выполнив инструкции в разделе [Пример. Создание составного элемента управления с помощью C\#](../Topic/Walkthrough:%20Authoring%20a%20Composite%20Control%20with%20Visual%20C%23.md). Не создавайте элемент управления "Будильник".  
  
> [!NOTE]
>  В дальнейших инструкциях предполагается, что вы присвоили элементу управления "Часы" имя `ctlClock`.  
  
## Создание расширения окна инструментов  
  
1.  Создайте проект VSIX с именем `MyToolWindowPackageUC`, который содержит окно инструментов с именем `MyToolWindow`. Если вам необходима помощь, см. раздел [Создание расширения с помощью окна инструментов](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## Добавление пользовательского элемента управления  
  
1.  В **обозревателе решений** щелкните решение **MyToolWindowPackageUC** правой кнопкой мыши, наведите указатель на пункт **Добавить** и выберите пункт **Существующий проект**.  
  
2.  В диалоговом окне **Добавление существующего проекта** откройте проект ctlClockLib и выберите файл проекта ctlClock.lib.csproj. Нажмите кнопку **ОК**. Будет активирован пользовательский элемент управления, который можно использовать в конструкторе.  
  
3.  В **обозревателе решений** щелкните правой кнопкой мыши файл MyToolWindowControl.cs и выберите команду **Открыть в конструкторе**. Откроется конструктор форм, в котором показан элемент управления, созданный для окна инструментов.  
  
4.  Откройте **панель элементов**, найдите раздел **Компоненты ctlClockLib** и дважды щелкните в нем элемент управления **ctlClock**, чтобы добавить его в форму. Когда вы скроете **панель элементов**, вы увидите циферблат в форме окна инструментов.  
  
5.  В конструкторе выберите только что добавленный элемент управления "Часы" и измените значение свойства **Anchor** на **Top**.  
  
6.  В **обозревателе решений** щелкните правой кнопкой мыши узел проекта ctlClockLib и выберите пункт **Свойства**.  
  
7.  На вкладке **Подписывание** выберите команду **Подписать сборку**. В поле **Выберите файл ключа строгого имени** щелкните **\<обзор\>** и перейдите к файлу key.snk в папке проекта **MyToolWindowPackageUC**.  
  
8.  Скомпилируйте программу и убедитесь в отсутствии ошибок. В этом шаге пакет VSPackage и его окно инструментов регистрируются в Visual Studio.  
  
9. Нажмите клавишу F5, чтобы открыть экземпляр Visual Studio в экспериментальном кусте.  
  
10. В экспериментальном экземпляре Visual Studio в меню **Вид** наведите указатель на пункт **Другие окна** и выберите пункт **MyToolWindow**. Откроется окно инструментов с работающими часами.  
  
## См. также  
 [Пример. Создание составного элемента управления с помощью C\#](../Topic/Walkthrough:%20Authoring%20a%20Composite%20Control%20with%20Visual%20C%23.md)