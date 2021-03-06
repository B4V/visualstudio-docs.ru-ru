---
title: AddMessage | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b60f8bac24b01e39327357b89e9e96c04765077
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49249006"
---
# <a name="addmessage"></a>AddMessage
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Добавляет пользовательское сообщение диагностики графики *HUD* (головной дисплей).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void AddMessage(  
  wchar_t const * szMessage  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `szMessage`  
 Сообщение, добавляемое на HUD.  
  
## <a name="remarks"></a>Примечания  
 Головной дисплей (HUD) диагностики графики отображается в левом верхнем углу приложения, которое работает в режиме диагностики графики. На нем отображаются сведения о приложении во время выполнения и о захвате данных графики, а также сообщения, добавленные путем вызова этой функции.  
  
 Чтобы добавить сообщение на HUD, у вас нет активный захват графической информации — то есть сообщение можно добавить посредством экземпляра `VsgDbg` класса, но [Init](../debugger/init.md) функция-член не должны вызываться сначала. Сообщения только отображаются на HUD; в файл журнала графики они не записываются.



