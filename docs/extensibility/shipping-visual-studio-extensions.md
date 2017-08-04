---
title: "Расширения Visual Studio доставки | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Развертывание VSIX"
  - "Развертывание VSIX"
  - "вспомогательные библиотеки DLL, в пакеты VSIX"
ms.assetid: 13cd263d-25f7-488e-9c1a-cff908caedb6
caps.latest.revision: 26
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 26
---
# Расширения Visual Studio доставки
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

После завершения разработки расширения, можно установить его на других компьютерах, сообщайте своим друзьям и коллегам или опубликовать его в коллекции Visual Studio. В этом разделе мы расскажем, все, что необходимо сделать, чтобы опубликовать и поддерживать расширение: работа с VSIX\-файлы, публикации, локализация и обновление.  
  
## Работа с расширений VSIX  
 Расширения VSIX можно создать путем создания пустой проект VSIX и добавление шаблонов различных элементов. Для получения дополнительной информации см. [Шаблон проекта VSIX](../extensibility/vsix-project-template.md).  
  
 Можно использовать формат VSIX в пакет шаблонов проектов, шаблонов, пакеты VSPackage, компоненты Managed Extensibility Framework \(MEF\), элемент **элементов** элементов управления, сборок и пользовательских типов \(включая настраиваемые начальные страницы\). Формат VSIX использует развертывания на основе файлов. Дополнительные сведения о пакетах VSIX см. в разделе [Составляющие пакета VSIX](../extensibility/anatomy-of-a-vsix-package.md).  
  
 Формат VSIX не поддерживает установку фрагментов кода. Он также не поддерживает некоторых сценариях, таких как запись в глобальный кэш сборок \(GAC\) или в системный реестр. Если необходимо выполнить запись в глобальном кэше СБОРОК или реестра в установке, необходимо использовать установщик Windows. Для получения дополнительной информации см. [Подготовка расширения для развертывания установщика Windows](../extensibility/preparing-extensions-for-windows-installer-deployment.md).  
  
## Публикация расширения в коллекции Visual Studio  
 Расширения другим пользователям можно распространять путем рассылки их VSIX\-файл, или помещать в на сервере. Лучший способ получить код в руки со многими людьми, то чтобы поместить его [коллекции Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847). Расширения в коллекции Visual Studio доступны для пользователей Visual Studio с помощью **расширения и обновления**. Для получения дополнительной информации см. [Поиск и использование расширений Visual Studio](../ide/finding-and-using-visual-studio-extensions.md).  
  
 Полный пример, в котором показано, как отправить расширения в коллекции Visual Studio, в разделе [Пошаговое руководство: Публикация расширения Visual Studio](../extensibility/walkthrough-publishing-a-visual-studio-extension.md).  
  
## Частные коллекции  
 При разработке элементов управления, шаблоны и средства, можно предоставить их организации, публикуя их частной коллекции в интрасети. Дополнительные сведения см. в разделе [Частные коллекции](../extensibility/private-galleries.md).  
  
## Локализация расширения  
 Если планируется выпуск расширения в разных языковых стандартов, следует рассмотреть возможность локализации. Объяснение, что именно задействуется, в разделе [Локализация пакетов VSIX](../extensibility/localizing-vsix-packages.md).  
  
## Обновление и модуль управления версиями  
 После публикации расширения придет время, когда необходимо обновить его. Чтобы узнать, как обновить расширения, которая была опубликована в галерее Visual Studio, см. раздел [Практическое руководство: обновление расширения](../extensibility/how-to-update-a-visual-studio-extension.md).  
  
 Можно установить расширения для поддержки нескольких версий Visual Studio. Для получения дополнительной информации см. [Поддержка нескольких версий Visual Studio](../extensibility/supporting-multiple-versions-of-visual-studio.md).  
  
## Связанные разделы  
  
|Заголовок|Описание|  
|---------------|--------------|  
|[Приступая к работе с использованием шаблона проекта VSIX](../extensibility/getting-started-with-the-vsix-project-template.md)|Объясняется, как использовать шаблон проекта VSIX для установки пользовательского шаблона проекта.|  
|[Составляющие пакета VSIX](../extensibility/anatomy-of-a-vsix-package.md)|Компоненты пакета VSIX.|  
|[Шаблон проекта VSIX](../extensibility/vsix-project-template.md)|Содержит пошаговые инструкции о том, как упаковка и публикация расширения.|  
|[Локализация пакетов VSIX](../extensibility/localizing-vsix-packages.md)|Способы предоставления локализованного текста для процесса установки с помощью файлов extension.vsixlangpack.|  
|[Практическое руководство: обновление расширения](../extensibility/how-to-update-a-visual-studio-extension.md)|Описывает Обновление расширения в системе и развернуть обновление существующего расширения Visual Studio.|  
|[Практическое руководство: Добавление зависимости пакета VSIX](../extensibility/how-to-add-a-dependency-to-a-vsix-package.md)|Описывает, как добавить ссылки на пакеты развертывания VSIX.|  
|[Подготовка расширения для развертывания установщика Windows](../extensibility/preparing-extensions-for-windows-installer-deployment.md)|Описание способов развертывания расширения с помощью установщика Windows.|  
|[Подписывание пакетов VSIX](../extensibility/signing-vsix-packages.md)|Объясняется, как подписывать пакеты VSIX.|  
|[Частные коллекции](../extensibility/private-galleries.md)|Описывается создание частных коллекций для расширений.|  
|[Поддержка нескольких версий Visual Studio](../extensibility/supporting-multiple-versions-of-visual-studio.md)|Показано, как для расширения поддержки нескольких версий Visual Studio.|