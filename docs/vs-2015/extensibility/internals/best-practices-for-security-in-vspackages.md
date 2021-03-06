---
title: Рекомендации по безопасности в пакетах VSPackage | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security [Visual Studio SDK]
- security best practices, VSPackages
- best practices, security
ms.assetid: 212a0504-cf6c-4e50-96b0-f2c1c575c0ff
caps.latest.revision: 20
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 80c27618582f42f1647e49cbf3f64d6b493dfd8d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49203597"
---
# <a name="best-practices-for-security-in-vspackages"></a>Рекомендации по обеспечению безопасности при использовании пакетов VSPackage
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Чтобы установить [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] на компьютере, необходимо использовать в контексте от имени администратора. Базовая единица безопасность и развертывание [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] приложение [пакетов VSPackage](../../extensibility/internals/vspackages.md). Необходимо зарегистрировать VSPackage с помощью [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], который также требуются административные учетные данные.  
  
 Администраторы имеют полные права доступа для записи в реестре и файловой системе, а также для выполнения любого кода. Необходимо иметь следующие разрешения для разработки, развертывания или установки пакетов VSPackage.  
  
 Как только установки VSPackage является полностью доверенным. Из-за высокий уровень разрешений, связанных с VSPackage существует возможность случайно установить пакет VSPackage, который злоумышленников.  
  
 Пользователям следует убедиться, что они установку пакетов VSPackage только из доверенных источников. Компании разработка пакетов VSPackage должен строго имени и подпишите их, для обеспечения предсказуемой, незаконное изменение запрещено. Разработка пакетов VSPackage компаниям следует проверить их внешние зависимости, такие как веб-службы и удаленной установки, чтобы оценить и устранить все проблемы безопасности.  
  
 Дополнительные сведения см. в разделе правил написания безопасного кода для .NET Framework ([http://msdn.microsoft.com/library/d55zzx87.aspx](http://msdn.microsoft.com/library/d55zzx87.aspx)).  
  
## <a name="see-also"></a>См. также  
 [Безопасность надстроек](http://msdn.microsoft.com/library/44a5c651-6246-4310-b371-65378917c799)   
 [Безопасность DDEX](http://msdn.microsoft.com/en-us/44a52a70-5c98-450e-993d-4a3b32f69ba8)

