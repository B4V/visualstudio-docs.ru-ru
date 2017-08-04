---
title: "Практическое руководство. Отладка ClickOnce-приложения с ограниченными разрешениями | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "отладка [Visual Studio], приложения ClickOnce"
  - "развертывание ClickOnce, отладка"
  - "приложения ClickOnce, отладка"
ms.assetid: 6991ea91-5253-451b-923d-22273a3d38b1
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Отладка ClickOnce-приложения с ограниченными разрешениями
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Как разработчик вы, скорее всего, работаете на компьютере разработчика с разрешениями полного доверия и поэтому не увидите те исключения безопасности, возникающие при отладке приложения ClickOnce, с которыми может столкнуться конечный пользователь, работающий с ограниченными разрешениями.  
  
 Чтобы перехватывать такие исключения, необходимо выполнять отладку приложения с теми же разрешениями, которые имеет конечный пользователь. Отладку с ограниченными разрешениями можно включить на странице **Безопасностьконструктора проектов**.  
  
 Кроме того, при разработке приложений, вызывающих веб\-службы, последние часто размещаются на компьютере разработчика. После развертывания конечный пользователь будет обращаться к этим веб\-службам по другому URL\-адресу. Чтобы эмулировать процедуру взаимодействия с пользователем во время отладки, можно указать URL\-адрес, заставив отладчик считать, что веб\-службы вызываются именно оттуда.  
  
### Включение отладки с ограниченными разрешениями  
  
1.  Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.  
  
2.  В **конструкторе проектов** перейдите на вкладку **Безопасность**.  
  
3.  Установите флажок **Включить параметры безопасности ClickOnce\-приложений**, а затем выберите переключатель **Это приложение с частичным доверием**.  
  
4.  Нажмите кнопку **Дополнительно**.  
  
5.  Установите флажок **Отладить это приложение с выбранным набором разрешений** и нажмите кнопку **ОК**.  
  
     При отладке приложения любые попытки доступа к разрешению, не входящему в набор разрешений, будут вызывать исключение безопасности.  
  
### Указание URL\-адреса для отладки  
  
1.  Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.  
  
2.  В **конструкторе проектов** перейдите на вкладку **Безопасность**.  
  
3.  Установите флажок **Включить параметры безопасности ClickOnce\-приложений**, а затем выберите переключатель **Это приложение с частичным доверием**.  
  
4.  Нажмите кнопку **Дополнительно**.  
  
5.  Установите флажок **Отладить это приложение с выбранным набором разрешений** и нажмите кнопку **ОК**.  
  
6.  В текстовом поле **Отладить это приложение как загруженное со следующего URL** введите URL\-адрес или сетевой путь.  
  
## См. также  
 [Практическое руководство. Установка пользовательских разрешений для ClickOnce\-приложения](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Защита приложений ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Управление доступом для кода для приложения ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [Защита приложений ClickOnce](../deployment/securing-clickonce-applications.md)