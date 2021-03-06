---
title: Практическое руководство. Настройка проектов для нескольких платформ | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio], targeting platforms
- platforms, changing target platforms
ms.assetid: affa2392-7aed-45ac-9ffa-1d8e0496d590
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9a3010e6304124ee306c5ecad3593df98d555523
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49921838"
---
# <a name="how-to-configure-projects-to-target-multiple-platforms"></a>Практическое руководство. Настройка проекта для нескольких платформ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] позволяет ориентировать решение сразу на несколько архитектур ЦП или платформ. Свойства для подобной настройки находятся в диалоговом окне **Диспетчер конфигураций**.  
  
## <a name="targeting-a-platform"></a>Ориентация на платформу  
 Диалоговое окно **Диспетчер конфигураций** позволяет создать и установить конфигурации и платформы на уровне решений и проектов. С каждым сочетанием конфигураций, относящихся к уровню решений, и целевых объектов может быть связан уникальный набор свойств, что позволяет легко переключаться между, например, конфигурацией выпуска, ориентированной на платформу [!INCLUDE[vcprx64](../includes/vcprx64-md.md)], конфигурацией выпуска, ориентированной на платформу x86, а также конфигурацией отладки, ориентированной на платформу x86.  
  
#### <a name="to-set-your-configuration-to-target-a-different-platform"></a>Настройка конфигурации для другой платформы  
  
1.  В меню **Сборка** щелкните элемент **Диспетчер конфигураций**.  
  
2.  В поле **Активная платформа решения** выберите платформу, на которую нужно ориентировать решение, или выберите **\<Создать >** для создания платформы. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] скомпилирует приложение для ориентацию на платформу, заданную в качестве активной в диалоговом окне **Диспетчер конфигураций**.  
  
## <a name="removing-a-platform"></a>Удаление платформы  
 Если вы понимаете, что платформа вам больше не нужна, то можете удалить ее из диалогового окна "Диспетчер конфигураций". Это приведет к удалению всех параметров решения и проекта параметры, настроенных для этого сочетания конфигурации и целевой платформы.  
  
#### <a name="to-remove-a-platform"></a>Порядок удаления платформы  
  
1.  В меню **Сборка** щелкните элемент **Диспетчер конфигураций**.  
  
2.  В списке **Активная платформа решения** выберите **\<Изменить>**. Открывается диалоговое окно **Изменение платформ решения**.  
  
3.  Выберите платформу, которую необходимо удалить, и нажмите кнопку **Удалить**.  
  
## <a name="targeting-multiple-platforms-with-one-solution"></a>Настройка одного решения для нескольких платформ  
 Так как вы можете изменять параметры на основе комбинации конфигурации и параметров платформы, можно настроить решение, предназначенное для нескольких платформ.  
  
#### <a name="to-target-multiple-platforms"></a>Настройка для нескольких платформ  
  
1.  Используйте **Диспетчер конфигураций**, чтобы добавить для решения по меньшей мере две целевые платформы.  
  
2.  Выберите нужную платформу в списке **Активная платформа решения**.  
  
3.  Постройте решение.  
  
#### <a name="to-build-multiple-solution-configurations-at-once"></a>Одновременное создание нескольких конфигураций решения  
  
1. Используйте **Диспетчер конфигураций**, чтобы добавить для решения по меньшей мере две целевые платформы.  
  
2. Используйте окно **Пакетная сборка** для создания нескольких конфигураций решения одновременно.  
  
   Можно задать в качестве платформы уровня решения, например [!INCLUDE[vcprx64](../includes/vcprx64-md.md)], при этом не имея в этом решении никаких других проектов, ориентированных на ту же платформу. Можно также иметь в решении несколько проектов, каждый из которых ориентирован на отдельную платформу. В такой ситуации рекомендуется создать конфигурацию с понятным именем, чтобы избежать путаницы.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Создание и изменение конфигураций](../ide/how-to-create-and-edit-configurations.md)   
 [Общие сведения о конфигурациях построения](../ide/understanding-build-configurations.md)   
 [Построение и очистка проектов и решений в Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)



