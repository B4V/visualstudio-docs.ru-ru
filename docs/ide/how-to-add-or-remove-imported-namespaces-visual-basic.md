---
title: "Практическое руководство. Добавление или удаление импортированных пространств имен (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adding imported namespaces
- removing imported namespaces
- namespaces [Visual Studio], imported
- imported namespaces [Visual Studio]
- references [Visual Studio], imported namespaces
ms.assetid: 44cebec3-0ea0-47c2-8406-4edeab6a997e
caps.latest.revision: 11
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
ms.openlocfilehash: f512673808ae3fab2fdcca39b58f77ca5df93e05
ms.contentlocale: ru-ru
ms.lasthandoff: 06/23/2017

---
# <a name="how-to-add-or-remove-imported-namespaces-visual-basic"></a>Практическое руководство. Добавление или удаление импортированных пространств имен (Visual Basic)
Импорт пространства имен позволяет использовать элементы из этого пространства имен в коде без полного определения элемента. Например, если требуется получить доступ к методу `Create` в классе `System.Messaging.MessageQueue`, можно импортировать пространство имен `System.Messaging` и просто обращаться к необходимому элементу в коде в виде `MessageQueue.Create`.  

 Для управления импортированными пространствами имен служит страница **Ссылки** **конструктора проектов**. Импортированные пространства имен, указанные в этом окне, передаются непосредственно в компилятор (`/imports`) и применяются ко всем файлам в проекте. Примените инструкцию `Imports` для использования пространства имен в одном файле исходного кода.  

### <a name="to-add-an-imported-namespace"></a>Добавление импортированного пространства имен  

1.  В **обозревателе решений** дважды щелкните узел проекта **Мой проект**.  

2.  В **конструкторе проектов** перейдите на вкладку **Ссылки**.  

3.  В списке **Импортированные пространства имен** установите флажок для пространства имен, которое необходимо добавить.  

    > [!NOTE]
    >  Поддерживается импорт только тех пространств имен, которые содержатся в указанном компоненте. Если пространство имен не отображается в списке, необходимо добавить ссылку на компонент, который его содержит. Дополнительные сведения см. в статье [Управление ссылками в проекте](managing-references-in-a-project.md).  
  
### <a name="to-remove-an-imported-namespace"></a>Удаление импортированного пространства имен  

1.  В **обозревателе решений** дважды щелкните узел проекта **Мой проект**.  

2.  В **конструкторе проектов** перейдите на вкладку **Ссылки**.  

3.  В списке **Импортированные пространства имен** снимите флажок для пространства имен, которое требуется удалить.  

## <a name="user-imports"></a>Пользовательский импорт  
 Функция пользовательского импорта позволяет импортировать определенный класс в пространстве имен, вместо всего пространства имен. Например, для приложения может быть доступен импорт пространства имен `Systems.Diagnostics`, но в этом пространстве имен вас интересует только класс `Debug`. Вы можете определить `System.Diagnostics.Debug` как пользовательский импорт, а затем удалить импорт `System.Diagnostics`.  

 Если позже вы передумаете и решите, что на самом деле вам нужен был класс `EventLog`, можно ввести `System.Diagnostics.EventLog` как пользовательский импорт и перезаписать `System.Diagnostics.Debug` с помощью функции изменения.  

#### <a name="to-add-a-user-import"></a>Добавление пользовательского импорта  

1.  В **обозревателе решений** дважды щелкните узел проекта **Мой проект**.  

2.  В **конструкторе проектов** перейдите на вкладку **Ссылки**.  

3.  В текстовом поле под списком **Импортированные пространства имен** введите полное имя пространства имен, которое вы хотите импортировать, включая корневое пространство имен.  

4.  Нажмите кнопку **Добавить пользовательский импорт**, чтобы добавить пространство имен в список **Импортированные пространства имен**.  

    > [!NOTE]
    >  Кнопка **Добавить пользовательский импорт** будет отключена, если пространство имен совпадает с одним из указанных в списке: импорт невозможно добавить дважды.  

#### <a name="to-update-a-user-import"></a>Изменение пользовательского импорта  

1.  В **обозревателе решений** дважды щелкните узел проекта **Мой проект**.  

2.  В **конструкторе проектов** перейдите на вкладку **Ссылки**.  

3.  В списке **Импортированные пространства имен** выберите пространство имен, которое необходимо изменить.  

4.  В текстовом поле под списком **Импортированные пространства имен** введите имя для нового пространства имен.  

5.  Нажмите кнопку **Обновить пользовательский импорт**, чтобы обновить пространство имен в списке **Импортированные пространства имен**.  

## <a name="see-also"></a>См. также  
 [Управление ссылками в проекте](../ide/managing-references-in-a-project.md)
