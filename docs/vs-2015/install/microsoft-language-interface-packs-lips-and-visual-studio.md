---
title: Пакеты Microsoft интерфейса (LIP) и Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text [Visual Studio], multiple languages
- Multilingual User Interface [Visual Studio]
- language switching [Visual Studio]
- MUI [Visual Studio]
- multiple language support [Visual Studio SDK]
- Windows Multilingual User Interface
- UI text language [Visual Studio]
- languages, multiple language support
ms.assetid: dc86304b-65b7-47e6-9314-1dfd02ecfa65
caps.latest.revision: 28
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 72c71ae80dfd44752e03f1d4fd7fd384adc13dfc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49812885"
---
# <a name="microsoft-language-interface-packs-lips-and-visual-studio"></a>Пакеты интерфейса пользователя (Microsoft LIP) и Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

С помощью языкового пакета интерфейса Windows (LIP) можно устанавливать языковую версию Windows и затем устанавливать различные языковые пакеты пользовательского интерфейса. Языковые пакеты пользовательского интерфейса предоставляют локализованный пользовательский интерфейс (UI) для операционных систем. Например, можно установить японский языковой пакет интерфейса на английскую версию Windows, а затем переключать интерфейс пользователя Windows между японским и английским языками. С помощью пакетов LIP можно получить несколько языковых версий Windows на одном компьютере.  
  
 На компьютерах с установленными пакетами LIP и несколькими языковыми версиями среды разработки Visual Studio при изменении языка интерфейса Windows автоматически изменяется язык интерфейса пользователя Visual Studio, если установлен соответствующий пакет.  
  
## <a name="limitations-of-multi-language-installations"></a>Ограничения многоязыковых установок  
 При установке различных языковых версий Visual Studio на одном компьютере возможно только переключение языков между соответствующими выпусками. Например, если на компьютере установлен английский экспресс-выпуск, немецкий экспресс-выпуск и выпуск Professional Edition, то языки можно переключать только для экспресс-выпусков, а для выпуска Professional Edition — нет.  
  
 В Visual Studio используется унифицированный языковой пакет. Чтобы установить несколько языковых версий этих продуктов, необходимо сначала установить полный продукт с поддержкой языка, а затем установить один или несколько языковых пакетов.  
  
> [!NOTE]
>  Visual Studio не поддерживает установку нескольких языковых версий полного языкового продукта на одном компьютере. После установки одного полного языкового продукта необходимо добавить версии языков с помощью языковых пакетов. Можно по-прежнему установить несколько полных языковых продуктов выпусков Express на одном и том же компьютере.  
  
### <a name="support-for-code-pages"></a>Поддержка кодовых страниц  
 Некоторые средства среды разработки Visual Studio неправильно отображают текст, если он содержит символы, не входящие в текущую кодовую страницу. Вместо текста отображаются вопросительные знаки или текст отображается неправильно. Это ограничение распространяется на следующие средства и области:  
  
-   Сайты, разворачиваемые через FTP.  
  
-   Имена компьютеров, содержащие не входящие в набор ASCII символы, в некоторых элементах управления.  
  
-   средства командной строки, выполняемые вне среды разработки Visual Studio;  
  
-   мастер миграции Visual Basic Migration Wizard;  
  
-   контейнер ActiveX Control Test Container;  
  
-   программа просмотра объектов OLE/COM;  
  
-   средство ISAPI Web Debug;  
  
-   Проекты приложений MFC с содержимым справки в формате HTML.  
  
-   В случае несовместимой кодовой страницы ИП Visual SourceSafe / SCCI переключается на английский язык.  
  
-   Средство Visual SourceSafe не поддерживает имена файлов в формате Юникод.  
  
-   Определяемые конечным пользователем символы (зона закрытого использования) не могут использоваться в качестве токенов или идентификаторов.  
  
-   Символы кодовой таблицы "Расширенная латиница-B" не отображаются в некоторых окнах инструментов Visual Studio, если для Windows задана кодовая таблица для восточноазиатских языков.  
  
-   Фрагменты текста, состоящие из символов многоязыковых скриптов, могут отображаться с использованием глифов по умолчанию для некоторых символов.  
  
-   При копировании и вставке строк с наборами сложных знаков в общих элементах управления могут теряться параметры текста. Для правильного ввода используйте соответствующую раскладку клавиатуры.  
  
##### <a name="to-correctly-display-characters-that-are-not-included-in-the-current-code-page"></a>Для правильного отображения символов, не входящих в текущую кодовую страницу  
  
1.  Нажмите кнопку **запустить**, нажмите кнопку **панели управления**и откройте **язык и региональные стандарты** (или **регион** в [!INCLUDE[win8](../includes/win8-md.md)]).  
  
    > [!NOTE]
    >  Для выполнения этих действий требуются права администратора.  
  
2.  Откройте вкладку **Дополнительно** .  
  
3.  В **выберите язык, соответствующий языку используемых программ не в Юникоде, необходимо использовать** выберите язык, используемой в текущий момент.  
  
4.  Нажмите кнопку **ОК**.  
  
## <a name="changing-the-language-used-for-the-ui-text-in-visual-studio"></a>Изменение языка, используемого для текста интерфейса пользователя в среде разработки Visual Studio  
 При установке нескольких языковых версий [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] на одном компьютере, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] пользовательского интерфейса по умолчанию равно **такой же, как Microsoft Windows**. Этот параметр указывает, что [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] будет отображать текст ИП на языке, заданном в качестве языка отображения для операционной системы.  
  
> [!NOTE]
>  Если Visual Studio настроен на использование **такой же, как Microsoft Windows**и соответствующий языковой пакет для Visual Studio не установлен, Visual Studio будет использовать язык первой установки Visual Studio.  
  
#### <a name="to-set-the-language-that-is-used-for-the-ui-text-in-visual-studio"></a>Установка языка, используемого для текста интерфейса пользователя среды разработки Visual Studio  
  
1. В меню **Сервис** выберите пункт **Параметры**.  
  
2. В **параметры** диалогового окна разверните узел **среды** и нажмите кнопку **международных настроек**.  
  
3. В **языка** выберите язык, в которой должен отображаться текст пользовательского интерфейса в среде разработки.  
  
    Чтобы текст пользовательского интерфейса в интегрированной среде разработки соответствовал языку операционной системы, выберите **такой же, как Microsoft Windows**.  
  
   Можно также использовать команду devenv для задания языка, используемого для пользовательского интерфейса. Дополнительные сведения см. в разделе [/LCID (devenv.exe)](../ide/reference/lcid-devenv-exe.md).  
  
## <a name="see-also"></a>См. также  
 [Страница "Язык интерфейса", папка "Среда", диалоговое окно "Параметры"](../ide/reference/international-settings-environment-options-dialog-box.md)