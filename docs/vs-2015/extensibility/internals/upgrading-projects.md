---
title: Обновление проектов | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading VSPackages
- upgrading applications, strategies
- VSPackages, upgrade support
ms.assetid: e01cb44a-8105-4cf4-8223-dfae65f8597a
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 74ec29dbc4aae393d9ee09fa6a9de273369ce7cb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47559965"
---
# <a name="upgrading-projects"></a>Обновление проектов
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [обновление проектов](https://docs.microsoft.com/visualstudio/extensibility/internals/upgrading-projects).  
  
Изменения в модель проекта из одной версии [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] к следующему может потребоваться обновление проектов и решений, чтобы они могут работать на более новой версии. [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] Предоставляет интерфейсы, которые могут использоваться для реализации поддержки обновления в своих собственных проектах.  
  
## <a name="upgrade-strategies"></a>Стратегии обновления  
 Для поддержки обновления, реализации системы проекта необходимо определить и реализовать стратегию обновления. В определении стратегии, вы можете для поддержки резервного копирования side-by-side (SxS) и резервного копирования.  
  
-   Резервное копирование SxS означает, что проект копирует только те файлы, которые требуется обновление на месте, добавив подходящий файл суффикса имени, например, «расширения» OLD.  
  
-   Резервная копия для копирования означает, что проект копирует все элементы проекта папку резервного копирования, предоставляемый пользователем. Затем обновляются соответствующие файлы в исходное расположение проекта.  
  
## <a name="how-upgrade-works"></a>О принципах работы обновления  
 Если решения, созданного в более ранней версии [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] открывается в более новой версии, проверок интегрированной среды разработки, файл решения для определения того, если он должен быть обновлен. Если обновление является обязательным, **мастер обновления** запускается автоматически, чтобы ознакомить пользователя через процесс обновления.  
  
 При решении необходимо обновить, он запрашивает Каждая фабрика проекта для его обновления стратегии. Стратегия определяет, поддерживает ли фабрика проектов резервного копирования или резервного копирования SxS. Информация отправляется **мастер обновления**, который собирает сведения, необходимые для резервного копирования и пользователю предоставляются соответствующие флажки.  
  
### <a name="multi-project-solutions"></a>Многопроектные решения  
 Если решение содержит несколько проектов и стратегии обновления отличаются, например, при создании проекта C++, который поддерживает только резервное копирование SxS и проект веб-приложения поддерживают только резервного копирования, фабрик проектов должны согласовывать стратегии обновления.  
  
 Решение запрашивает Каждая фабрика проекта для <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>. Затем он вызывает <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject_CheckOnly%2A> см. в разделе, если файлы глобальных проектов требуется обновление и определение поддерживаемых стратегии обновления. **Мастер обновления** затем вызывается.  
  
 Как только пользователь завершит мастера <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> вызывается для каждой фабрики проекта для выполнения фактического обновления. Для упрощения резервного копирования, предоставляют методы интерфейса IVsProjectUpgradeViaFactory <xref:Microsoft.VisualStudio.Shell.Interop.SVsUpgradeLogger> службу для записи сведений о процессе обновления. Эта служба не может кэшироваться.  
  
 После обновления все соответствующие файлы глобального, каждая фабрика проекта можно создать экземпляр проекта. Реализация проекта должна поддерживать <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> Затем вызывается метод для обновления всех элементов соответствующего проекта.  
  
> [!NOTE]
>  <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> Метод не предоставляет службу SVsUpgradeLogger. Эту службу можно получить путем вызова <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A>.  
  
## <a name="best-practices"></a>Рекомендации  
 Используйте <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave> службы, чтобы проверить можно изменить файл, прежде чем изменять его, а затем сохранить их перед сохранением. Это поможет резервного копирования и обновления реализаций обрабатывать файлы проекта в системе управления версиями, файлы с недостаточно разрешений и т. д.  
  
 Используйте <xref:Microsoft.VisualStudio.Shell.Interop.SVsUpgradeLogger> службы во время всех этапов резервное копирование и обновление для предоставления сведений об успешности выполнения процесса обновления.  
  
 Дополнительные сведения о резервном копировании и обновление проектов см. в разделе комментариев для интерфейса IVsProjectUpgrade в vsshell2.idl.  
  
## <a name="see-also"></a>См. также  
 [Проекты](../../extensibility/internals/projects.md)   
 [Обновление пользовательских проектов](../../misc/upgrading-custom-projects.md)   
 [Обновление элементов проекта](../../misc/upgrading-project-items.md)
