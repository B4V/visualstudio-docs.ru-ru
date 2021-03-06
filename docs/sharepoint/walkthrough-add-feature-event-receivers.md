---
title: 'Пошаговое руководство: Добавление приемников событий компонентов | Документация Майкрософт'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, advanced packaging tools
- SharePoint development in Visual Studio, event receivers
- SharePoint development in Visual Studio, feature event receivers
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4ab2eded41d9416f03592c9346a379f8a276366a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49948785"
---
# <a name="walkthrough-add-feature-event-receivers"></a>Пошаговое руководство: Добавление приемников событий компонентов
  Приемники событий приведены методы, которые выполняются при возникновении одного из следующих событий, связанных с функции в SharePoint.

- Установки компонента.

- Он активируется.

- Отключение компонента.

- Удаление компонента.

  В этом пошаговом руководстве показано, как добавить приемник событий компонента в проекте SharePoint. Он демонстрирует следующие задачи:

- Создание пустого проекта с приемником событий компонента.

- Обработка **FeatureDeactivating** метод.

- С помощью объектной модели project SharePoint добавить объявление в список объявлений.

  [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="prerequisites"></a>Предварительные требования
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.

-   Поддерживаемые редакции Microsoft Windows и SharePoint.

-   Visual Studio.

## <a name="create-a-feature-event-receiver-project"></a>Создание проекта приемника событий компонента
 Во-первых создайте проект, содержащий приемника событий компонента.

#### <a name="to-create-a-project-with-a-feature-event-receiver"></a>Создание проекта с приемником событий компонента

1.  В строке меню выберите **файл** > **New** > **проекта** для отображения **новый проект** диалоговое окно.

2.  Разверните **SharePoint** расположенный в области **Visual C#** или **Visual Basic**, а затем выберите **2010** узла.

3.  В **шаблоны** панели выберите **проект SharePoint 2010** шаблона.

     Этот тип проекта предназначен для приемников событий компонентов, поскольку для них не существует шаблона проекта.

4.  В **имя** введите **FeatureEvtTest**, а затем выберите **ОК** кнопку, чтобы отобразить **мастер настройки SharePoint**.

5.  На **Укажите сайт и уровень безопасности для отладки** странице, введите URL-адрес сайта сервера SharePoint, к которому требуется добавить пользовательский элемент поля или используйте расположение по умолчанию (http://\<*системы имя*> /).

6.  В **Какова степень доверия для этого решения SharePoint?** выберите **развернуть как решение фермы** переключатель.

     Дополнительные сведения об изолированных решениях и решений фермы см. в разделе [замечания об изолированных решениях](../sharepoint/sandboxed-solution-considerations.md).

7.  Выберите **Готово** кнопку, а затем Обратите внимание, что это функция с именем Feature1 находится в узле **функции** узла.

## <a name="add-an-event-receiver-to-the-feature"></a>Добавить приемник событий компонента
 Затем добавить приемник событий в компонент и добавьте код, который выполняется при отключении компонента.

#### <a name="to-add-an-event-receiver-to-the-feature"></a>Чтобы добавить приемник событий компонента

1.  Откройте контекстное меню для узла компонентов, а затем выберите **добавить компонент** создавать характеристики.

2.  В разделе **функции** узел, откройте контекстное меню для **Feature1**и нажмите кнопку **добавить приемник событий** для добавления приемника событий в компонент.

     Добавляется файл кода в разделе Feature1. В этом случае он имеет имя либо *Feature1.EventReceiver.cs* или *Feature1.EventReceiver.vb*, в зависимости от языка разработки проекта.

3.  Если проект написан на [!INCLUDE[csprcs](../sharepoint/includes/csprcs-md.md)], добавьте следующий код в начало приемника событий, если он еще не находится там:

     [!code-csharp[SP_FeatureEvt#1](../sharepoint/codesnippet/CSharp/featureevttest2/features/feature1/feature1.eventreceiver.cs#1)]

4.  Класс приемника событий содержит несколько закомментированных методов, действующих как события. Замените **FeatureDeactivating** следующим кодом:

     [!code-vb[SP_FeatureEvt#2](../sharepoint/codesnippet/VisualBasic/featureevt2vb/features/feature1/feature1.eventreceiver.vb#2)]
     [!code-csharp[SP_FeatureEvt#2](../sharepoint/codesnippet/CSharp/featureevttest2/features/feature1/feature1.eventreceiver.cs#2)]

## <a name="test-the-feature-event-receiver"></a>Тестирование приемника событий компонента
 Затем отключите компонент, чтобы протестировать ли **FeatureDeactivating** метод выводит объявление списка извещений SharePoint.

#### <a name="to-test-the-feature-event-receiver"></a>Для тестирования приемника событий компонента

1.  Установите для параметра проекта **активная конфигурация развертывания** свойства **без активации**.

     Задание этого свойства предотвращает возможность активации в SharePoint и можно выполнять отладку приемников событий компонентов. Дополнительные сведения см. в разделе [решений SharePoint Отладка](../sharepoint/debugging-sharepoint-solutions.md).

2.  Выберите **F5** клавишу, чтобы запустить проект и его развертывания в SharePoint.

3.  В верхней части веб-страницы SharePoint, откройте **действия сайта** меню, а затем выберите **параметры сайта**.

4.  В разделе **действия сайта** раздел **параметры сайта** выберите **Управление компонентами сайта** ссылку.

5.  На **функции** выберите **активировать** рядом с пунктом **FeatureEvtTest Feature1** функции.

6.  На **функции** выберите **деактивировать** рядом с пунктом **FeatureEvtTest Feature1** компонентов и нажмите кнопку **деактивировать этот компонент**  ссылку для подтверждения деактивировать функцию.

7.  Выберите **Главная** кнопки.

     Обратите внимание, что появилось объявление в **объявления** вывести после отключения компонента.

## <a name="see-also"></a>См. также

- [Практическое: Создание приемника событий](../sharepoint/how-to-create-an-event-receiver.md)
- [Разработка решений SharePoint](../sharepoint/developing-sharepoint-solutions.md)