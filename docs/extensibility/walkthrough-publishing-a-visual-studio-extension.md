---
title: "Пошаговое руководство: Публикация расширения Visual Studio | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing web controls
- web controls, publishing
ms.assetid: a7816161-0490-4043-86f5-0f7331ed83b3
caps.latest.revision: 17
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: 574af4ff2b3858201c13121475de02a763572f6b
ms.openlocfilehash: fcfb0724b89d60553d6686a0705ab1e9459014ce
ms.lasthandoff: 02/22/2017

---
# <a name="walkthrough-publishing-a-visual-studio-extension"></a>Пошаговое руководство: Публикация расширения Visual Studio
В этом пошаговом руководстве показано, как для публикации расширения Visual Studio в коллекции Visual Studio. При добавлении расширения в коллекции, разработчики могут использовать **расширения и обновления** для просмотра есть новые и обновленные модули.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения этого пошагового руководства необходимо установить пакет SDK для Visual Studio. Дополнительные сведения см. в разделе [пакет SDK для Visual Studio](../extensibility/visual-studio-sdk.md).  
  
## <a name="create-a-visual-studio-extension"></a>Создание расширения Visual Studio  
 В этом случае мы используем расширение VSPackage по умолчанию, но допустимы те же действия для каждого типа расширения.  
  
1.  Создать пакет VSPackage в C# с именем `TestPublishing` , есть команда меню. Дополнительные сведения см. в разделе [создания расширения с командой меню](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
## <a name="test-the-extension"></a>Тестирование расширения  
 Перед распространением расширение построения и тестирования его, чтобы убедиться, что он правильно установлен в экспериментальном экземпляре Visual Studio.  
  
1.  В Visual Studio запустите отладку. Чтобы открыть экспериментальный экземпляр Visual Studio.  
  
2.  В экспериментальном экземпляре откройте **средства** меню и выберите пункт **Диспетчер расширений**. Расширение TestPublishing появится в центральной области и включить.  
  
3.  На **средства** меню, убедитесь, что вы видите эту команду теста.  
  
## <a name="publish-the-extension-to-the-visual-studio-gallery"></a>Публикация расширения в коллекции Visual Studio  
 Теперь можно опубликовать расширения в коллекции Visual Studio.  
  
1.  Убедитесь, что вы создали версии расширения и его актуален.  
  
2.  В веб-браузере откройте веб-сайт [коллекции Visual Studio](http://go.microsoft.com/fwlink/?LinkId=194329) .  
  
3.  В правом верхнем углу, выберите **входа в**.  
  
4.  Войдите с помощью своей учетной записи Майкрософт. Если у вас учетная запись Майкрософт, можно создать один на этом этапе.  
  
5.  Нажмите кнопку **Выгрузка**.  
  
6.  В **шаг 1: тип расширения**выберите **средство** и нажмите кнопку **Далее**.  
  
7.  В **шаг 2: Отправка**, можно отправить непосредственно в коллекции Visual Studio или просто добавить ссылку для вашего веб-сайта. В этом случае выберите **я хотел бы передать свое средство**. **Выберите ваш элемент управления** откроется окно. Щелкните **Обзор** и выберите TestPublish.vsix в папке \bin\Release проекта. Нажмите кнопку **Далее**.  
  
8.  В **шаг 3: основные сведения**, отображаются поля в файле source.extension.vsixmanifest. Выберите соответствующее **категории** и добавьте **теги** для упрощения поиска расширения. Можно добавить дополнительные сводку и описание (Описание должно быть по крайней мере 280 символов). Оставить **тип расширения** как **не расширение Microsoft** и **категории затрат** как **пробная версия**.  
  
9. Чтение соглашение об участии в нижней части страницы и проверьте **принимаю**.  
  
10. Щелкните **Создание публикации**. Откроется страница, будут иметь расширения в коллекции Visual Studio с сообщением, что страница еще не опубликован.  
  
11. Нажмите кнопку **Опубликовать**.  
  
12. Поиск в коллекции Visual Studio для расширения. Появится список для расширения TestPublish.  
  
## <a name="install-the-extension-from-the-visual-studio-gallery"></a>Установка расширения из коллекции Visual Studio  
 Теперь, когда публикуется расширения, установите его в Visual Studio и протестируйте его.  
  
1.  В Visual Studio на **средства** меню, щелкните **расширения и обновления**.  
  
2.  Щелкните **Online** и выполните поиск TestPublish. Появится список для расширения TestPublish.  
  
3.  Нажмите **Загрузить**. После скачивания расширения нажмите кнопку **Установить**.  
  
4.  Чтобы завершить установку, перезапустите Visual Studio.  
  
## <a name="removing-the-extension"></a>Удаление расширения  
 Расширение можно удалить из коллекции Visual Studio и с компьютера.  
  
#### <a name="to-remove-the-extension-from-the-visual-studio-gallery"></a>Чтобы удалить расширения из коллекции Visual Studio  
  
1.  Откройте [коллекции Visual Studio](http://go.microsoft.com/fwlink/?LinkId=194329) веб-сайта.  
  
2.  В центре, щелкните **Мои расширения**. Отображается список для TestPublish.  
  
3.  Щелкните **удаление**.  
  
#### <a name="to-remove-the-extension-from-your-computer"></a>Чтобы удалить расширение с компьютера  
  
1.  В меню **Сервис** Visual Studio выберите пункт **Диспетчер расширений**.  
  
2.  Выберите TestPublish и нажмите кнопку **удаление**.  
  
3.  Чтобы завершить удаление, перезапустите Visual Studio.
