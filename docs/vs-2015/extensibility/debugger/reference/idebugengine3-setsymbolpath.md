---
title: IDebugEngine3::SetSymbolPath | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEngine3::SetSymbolPath
helpviewer_keywords:
- IDebugEngine3::SetSymbolPath
ms.assetid: 47b48f84-8a96-401f-84df-0baa8a96d26e
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f74fafc325693df6a312647c9e9060a24cf256ef
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49863559"
---
# <a name="idebugengine3setsymbolpath"></a>IDebugEngine3::SetSymbolPath
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Задает путь или пути, в которых производится поиск символов отладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp#  
HRESULT SetSymbolPath (  
   LPOLESTR            szSymbolSearchPath,  
   LPOLESTR            szSymbolCachePath,  
   LOAD_SYMBOLS_FLAGS  Flags  
);  
```  
  
```csharp  
int SetSymbolPath(  
   string                    szSymbolSearchPath,   
   string                    szSymbolCachePath,   
   enum_LOAD_SYMBOLS_FLAGS   Flags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`szSymbolSearchPath`|[in] Строка, содержащая путь поиска символов или пути. Дополнительные сведения см. «Примечания». Не может иметь значение NULL.|  
|`szSymbolCachePath`|[in] Строка, содержащая локальный путь, где можно кэшировать символы. Не может иметь значение NULL.|  
|`Flags`|[in] Не используется; всегда равен 0.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает значение S_OK; в противном случае возвращает код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Строка `szSymbolSearchPath` приведен список один или несколько путей, разделенных точкой с запятой, для поиска символов. Эти пути может быть локальный путь, UNC-стиле путь или URL-адрес. Эти пути, также могут быть смесью различных типов. Если путь является UNC (например, \\\Symserver\Symbols), а затем модуль отладки следует определить, если путь к серверу символов и должен иметь возможность загрузить символы с этого сервера, кэшируя их в путь, указанный `szSymbolCachePath`.  
  
 Путь к символам, также может содержать одно или несколько расположений кэша. Кэши первым в порядке приоритета, с наивысшим приоритетом кэша и разделены * символы. Пример:  
  
```  
\\symbols\symbols;\\someotherserver\symbols;c:\symbols\httpsymbols*http://msdl.microsoft.com  
```  
  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md) метод выполняет фактическое загрузку символов.  
  
## <a name="see-also"></a>См. также  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)   
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)

