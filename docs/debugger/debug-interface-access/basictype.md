---
title: BasicType | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BasicType enumeration
ms.assetid: 19ae53ba-cd6e-47b6-9f94-27ae663ce955
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 61d63f20bb086190f6409d3eb4cd08c80689d10f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49874024"
---
# <a name="basictype"></a>BasicType
Задает базовый тип символа.  
  
## <a name="syntax"></a>Синтаксис  
  
```C++  
enum BasicType {   
   btNoType   = 0,  
   btVoid     = 1,  
   btChar     = 2,  
   btWChar    = 3,  
   btInt      = 6,  
   btUInt     = 7,  
   btFloat    = 8,  
   btBCD      = 9,  
   btBool     = 10,  
   btLong     = 13,  
   btULong    = 14,  
   btCurrency = 25,  
   btDate     = 26,  
   btVariant  = 27,  
   btComplex  = 28,  
   btBit      = 29,  
   btBSTR     = 30,  
   btHresult  = 31  
   btChar16   = 32,  // char16_t
   btChar32   = 33,  // char32_t
};  
```  
  
## <a name="elements"></a>Элементы  
 btNoType  
 Базовый тип не указан.  
  
 btVoid  
 Базовый тип является `void`.  
  
 btChar  
 Базовый тип является `char` (C/C++ тип).  
  
 btWChar  
 Базовый тип представляет собой расширенный символ (Юникод) (`WCHAR`).  
  
 btInt  
 Базовый тип является `signed int` (C/C++ тип).  
  
 btUInt  
 Базовый тип является `unsigned int` (C/C++ тип).  
  
 btFloat  
 Базовый тип является числом с плавающей запятой (`FLOAT`).  
  
 btBCD  
 Базовый тип — это десятичное число закодированных двоичный файл (`BCD`).  
  
 btBool  
 Базовый тип является логическое значение (`BOOL`).  
  
 btLong  
 Базовый тип является `long int` (C/C++ тип).  
  
 btULong  
 Базовый тип является `unsigned long int` (C/C++ тип).  
  
 btCurrency  
 Базовый тип является валюты.  
  
 btDate  
 Базовый тип является даты и времени (`DATE`).  
  
 btVariant  
 Базовый тип является структурой типа переменной (`VARIANT`).  
  
 btComplex  
 Базовый тип — комплексного числа.  
  
 btBit  
 Базовый тип — несколько.  
  
 btBSTR  
 Базовый тип — строка базовый или binary (`BSTR`).  
  
 btHresult  
 Базовый тип является `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Возвращаемые значения в этом перечислении [IDiaSymbol::get_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md) метод.  
  
## <a name="requirements"></a>Требования  
 Заголовок: cvconst.h  
  
## <a name="see-also"></a>См. также  
 [Перечисления и структуры](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)   
 [IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)
