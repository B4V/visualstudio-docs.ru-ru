---
title: IDiaSymbol::get_stride | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 4264742a-3d91-44b9-9d14-87adbc77f0f0
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 08513c0ad94740f66dfd1d35d36c801c42a606ea
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49175373"
---
# <a name="idiasymbolgetstride"></a>IDiaSymbol::get_stride
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Извлекает stride, матрицы или strided массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT get_stride(   
   DWORD* pRetVal);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pRetVal`  
 [out] Указатель на `DWORD` , содержащий шаг.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает `S_FALSE` или код ошибки.  
  
## <a name="see-also"></a>См. также  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



