---
title: 'Ошибка: SQL может&#39;t обнаружить компонент SSDEBUGPS | Документация Майкрософт'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- FSharp
- VB
- CSharp
- C++
- SQL
ms.assetid: 596425c8-14c7-4c05-8823-e1c52f420f5e
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f775bd99c019a119d1bcd5193df0efd7ceadd096
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49180171"
---
# <a name="error-sql-can39t-find-ssdebugps"></a>Ошибка: SQL может&#39;t обнаружить компонент SSDEBUGPS
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Файл SSDEBUGPS.dll — компонент узла отладки SQL Server.  
  
 Эта ошибка возникает при попытке запустить отладку и указывает, что указанный файл не удается обнаружить на компьютере [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)]. Существуют две возможные причины этого: установка удаленной отладки не выполнялась или по каким-либо иным причинам файл был удален.  
  
 Существует два способа, чтобы устранить эту ошибку: повторное выполнение установки удаленной отладки и копирование файла на [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] машины.  
  
 Повторное выполнение установки удаленной отладки, следуйте инструкциям в [удаленной отладки](../debugger/remote-debugging.md).  
  
 Если есть возможность найти копию ssdebugps.dll, можно скопировать его на [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] машины. Этот файл должен быть в каталоге \Program Files\ Common Files\Microsoft Shared\SQL Debugging. Может оказаться на другом [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] компьютере или на компьютере, который имеет [!INCLUDE[vsprvslong](../includes/vsprvslong-md.md)] установлен.  
  
### <a name="to-copy-ssdebugpsdll-onto-the-sql-server-2005-machine"></a>Копирование файла SSDEBUGPS.dll на компьютер SQL Server 2005  
  
1.  Скопируйте файл в каталог с тем же именем и путем на [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] машины.  
  
2.  Зарегистрировать его, открыв **командной**и выполнив следующую команду:  
  
    ```  
    regsrv32 ssdebugps.dll  
    ```



