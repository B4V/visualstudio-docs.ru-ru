---
title: IDiaSectionContrib::get_uninitializedData | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_uninitializedData method
ms.assetid: 39736f35-6c73-4f54-a092-517192e417ff
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8f0929897f5dba77282fa056b5b1a00e05782c9f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49916326"
---
# <a name="idiasectioncontribgetuninitializeddata"></a>IDiaSectionContrib::get_uninitializedData
Получает флаг, указывающий, содержит ли раздел неинициализированных данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```C++  
HRESULT get_uninitializedData (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pRetVal`  
 [out] Возвращает `TRUE` Если раздел содержит неинициализированных данных; в противном случае возвращает `FALSE`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`. Возвращает `S_FALSE` Если это свойство не поддерживается. В противном случае возвращается код ошибки.  
  
## <a name="see-also"></a>См. также  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)