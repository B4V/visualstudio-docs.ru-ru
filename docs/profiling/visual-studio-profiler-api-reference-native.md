---
title: Справочник по API-интерфейсам профилировщика Visual Studio (машинный код) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, API
- Profiler, API
ms.assetid: a0c3be92-c263-4678-9fb9-bafead3bd5f5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: ba2590c17a41d200f0a8dd3c38c7c9ae8c8a85cc
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572102"
---
# <a name="visual-studio-profiler-api-reference-native"></a>Справочник по API-интерфейсам профилировщика Visual Studio (машинный код)
API-интерфейсы профилировщика Visual Studio позволяют программно управлять объемом собранных данных и вставлять метки времени и профиля во время профилирования. Чтобы использовать собственный API, включите файл заголовка *VSPerf.h* и добавьте файл *VSPerf.lib* в свой проект.  
  
> [!NOTE]
>  По умолчанию файлы *VSPerf.h* и *VSPerf.lib* расположены в папке с именем *PerfSDK*. Например, это может быть каталог *\<диск>:\Program Files\Microsoft Visual Studio 14.0\Team Tools\Performance Tools\PerfSDK*.  
  
## <a name="in-this-section"></a>Содержание раздела  
 [CommentMarkAtProfile](../profiling/commentmarkatprofile.md)  
  
 [CommentMarkProfile](../profiling/commentmarkprofile.md)  
  
 [MarkProfile](../profiling/markprofile.md)  
  
 [NameProfile](../profiling/nameprofile.md)  
  
 [ResumeProfile](../profiling/resumeprofile.md)  
  
 [StartProfile](../profiling/startprofile.md)  
  
 [StopProfile](../profiling/stopprofile.md)  
  
 [SuspendProfile](../profiling/suspendprofile.md)  
  
 [PROFILE_CURRENTID](../profiling/profile-currentid.md)  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы API средств профилирования](../profiling/profiling-tools-apis.md)   
 [Пошаговое руководство. Использование API-интерфейсов профилировщика](../profiling/walkthrough-using-profiler-apis.md)
