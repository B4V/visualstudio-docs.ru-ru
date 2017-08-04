---
title: "Приступая к работе с подключаемых модулей системы управления версиями | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "управление подключаемыми модулями источников, Приступая к работе"
  - "Приступая к работе, источника подключаемые модули управления"
ms.assetid: 46ac1f9f-4ecc-4a72-88d3-4c7e1647e1cb
caps.latest.revision: 21
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 21
---
# Приступая к работе с подключаемых модулей системы управления версиями
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Чтобы создать подключаемый модуль системы управления версиями, необходимо создать библиотека, реализующая функции, определенные в API системы управления версиями подключаемого модуля, а затем зарегистрировать библиотеку DLL с [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] сделать его доступным для использования в подсистеме управления версиями исходного кода.  
  
 3 Версии API системы управления версиями подключаемого модуля \(версии 1.1, 1,2 и 1.3\) доступны для подключаемых модулей системы управления версиями.  API системы управления версиями подключаемый модуль документированное здесь версии 1.3.  Он был разработан таким образом, чтобы быть полностью совместимым с версиями 1.1 и 1,2 модулей системы управления версиями, поддерживающий.  [Новые возможности в подключаемый модуль API версия системы управления версиями 1.3](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md) сведения секции новые функции, поддерживаемые в последней версии api\-интерфейса подключаемых модулей системы управления версиями.  
  
## В этом подразделе  
 [Практическое руководство: Установка подключаемого модуля системы управления версиями](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)  
 Описывает, как сделать записи реестра, необходимые затыкают в библиотеке DLL системы управления версиями.  
  
 [Новые возможности в подключаемый модуль API версия системы управления версиями 1.3](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md)  
 Содержит общие сведения о изменений, внесенных в API системы управления версиями вставляемому в версии 1.3.  
  
 [Новые возможности в подключаемый модуль API версия системы управления версиями 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)  
 Содержит общие сведения о изменений, внесенных в API системы управления версиями вставляемому в версии 1.2.  
  
## Связанные подразделы  
 [Подключаемые модули управления версиями](../../extensibility/source-control-plug-ins.md)  
 Предоставляет полный листинг всех элементов в api\-интерфейсе подключаемых модулей системы управления версиями.  
  
 [Создание подключаемого модуля системы управления версиями](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 Указывает пакет SDK для системы управления версиями подключаемый модуль и описывает включенные ресурсы.