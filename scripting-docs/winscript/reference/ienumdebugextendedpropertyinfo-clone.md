---
title: IEnumDebugExtendedPropertyInfo::Clone | Документация Майкрософт
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugExtendedPropertyInfo.Clone
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugExtendedPropertyInfo::Clone
ms.assetid: dd645cf6-bfb3-486c-829e-bb91a6639665
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 03e4dcd79d90806eab0d664b2a0cba428c03207c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49935332"
---
# <a name="ienumdebugextendedpropertyinfoclone"></a>IEnumDebugExtendedPropertyInfo::Clone
Создает перечислитель с тем же состоянием перечисления, что и текущий перечислитель.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Clone (  
   IEnumDebugExtendedPropertyInfo** ppEnum  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppEnum`  
 [out] Возвращает клонированный `IEnumDebugExtendedPropertyInfo` интерфейс.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает допустимый `HRESULT`, обычно `S_OK`.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IEnumDebugExtendedPropertyInfo](../../winscript/reference/ienumdebugextendedpropertyinfo-interface.md)