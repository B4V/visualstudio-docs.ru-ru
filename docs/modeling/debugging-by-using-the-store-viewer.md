---
title: Отладка с использованием средства просмотра хранилища
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, store viewer
- Domain-Specific Language, store
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: d26c66b6bcbab2eafe2ae8b01597ef09985dcfa8
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47858656"
---
# <a name="debugging-by-using-the-store-viewer"></a>Отладка с использованием средства просмотра хранилища
В окне просмотра Store, можно проверить состояние *хранения* используемые [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]. Средство просмотра Store отображает все элементы модели домена, которые находятся в конкретном магазине, а также свойства элемента и ссылки между элементами.

## <a name="opening-store-viewer"></a>Средство просмотра открывающей Store
 Находясь в экспериментальном построении Visual Studio, остановите кода в точке останова, где экземпляр хранилища содержит сведения о модели. Откройте средство просмотра Store, введя следующую команду в **Интерпретация** окна:

```csharp
Microsoft.VisualStudio.Modeling.Diagnostics.StoreViewer.Show(mystore);
```

> [!NOTE]
>  Необходимо заменить `mystore` с именем экземпляра хранилища. Кроме того при добавлении пространства имен в коде, можно ввести команды для отображения средства просмотра Store без полного пространства имен:
>
>  `using Microsoft.VisualStudio.Modeling.Diagnostics;`
>
>  `...`
>
>  `StoreViewer.Show(mystore);`

 `Show` Метод имеет несколько перегрузок. Экземпляр хранилища или секции можно указать в качестве параметра.

 Кроме того, можно поместить строку кода, отображается средство просмотра Store в любом месте в коде где параметр, передаваемый `Show` метод находится в области. Это действие откроет средство просмотра Store, когда строка кода выполняется как моментальный снимок содержимого хранилища.

### <a name="using-store-viewer"></a>С помощью средства просмотра Store
 Когда откроется средство просмотра Store, немодальное окно Windows Forms выглядит, как показано на следующем рисунке.

 ![](../modeling/media/storeviewer2.png) Средство просмотра Store

 Средство просмотра Store есть три области: левой, верхней правой области и нижней правой области. Левая панель – древовидное представление типов в `DomainDataDirectory` член хранилища. Разверните узел раздела, щелкните элемент в верхней правой области отображаются свойства этого элемента. Если элемент связан с другими элементами, дополнительные элементы отображаются в нижней правой области. Если дважды щелкнуть элемент в нижней правой области, элемент будет выделен в левой области.

## <a name="see-also"></a>См. также

- [Перемещение по модели и обновление модели в коде программы](../modeling/navigating-and-updating-a-model-in-program-code.md)