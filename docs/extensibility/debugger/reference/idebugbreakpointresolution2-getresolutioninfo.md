---
title: "IDebugBreakpointResolution2::GetResolutionInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBreakpointResolution2::GetResolutionInfo"
helpviewer_keywords: 
  - "IDebugBreakpointResolution2::GetResolutionInfo"
ms.assetid: 828cbdf6-b87d-4c45-be87-d87087b04a60
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugBreakpointResolution2::GetResolutionInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Возвращает сведения о разрешениях точки останова, описывающий эту точку останова.  
  
## Синтаксис  
  
```cpp#  
HRESULT GetResolutionInfo(   
   BPRESI_FIELDS       dwFields,  
   BP_RESOLUTION_INFO* pBPResolutionInfo  
);  
```  
  
```c#  
int GetResolutionInfo(   
   enum BPRESI_FIELDS   dwFields,  
   BP_RESOLUTION_INFO[] pBPResolutionInfo  
);  
```  
  
#### Параметры  
 `dwFields`  
 \[in\] сочетание пометит из [BPRESI\_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md) перечисление, которое определяет, какие поля  `pBPResolutionInfo` параметр заполнянным.  
  
 `pBPResolutionInfo`  
 \[out\] [BP\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) структура, который необходимо заполнить сведениями о данной точке останова.  
  
## Возвращаемое значение  
 В случае успеха возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## Пример  
 Следующий пример реализует этот метод для простого `CDebugBreakpointResolution` объект, предоставляющий  [IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md) интерфейс.  
  
```  
HRESULT CDebugBreakpointResolution::GetResolutionInfo(  
   BPRESI_FIELDS dwFields,  
   BP_RESOLUTION_INFO* pBPResolutionInfo)  
{    
   HRESULT hr;    
  
   if (pBPResolutionInfo)    
   {    
      // Copy the specified fields of the request information from the class  
      // member variable to the local BP_RESOLUTION_INFO variable.    
      hr = CopyBP_RESOLUTION_INFO(m_bpResolutionInfo,  
                                  *pBPResolutionInfo,  
                                  dwFields);    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
  
HRESULT CDebugBreakpointResolution::CopyBP_RESOLUTION_INFO(  
   BP_RESOLUTION_INFO& bpResSrc,  
   BP_RESOLUTION_INFO& bpResDest,  
   DWORD dwFields)    
{    
   HRESULT hr = S_OK;    
  
   // Start with a raw copy.    
   memcpy(&bpResDest, &bpResSrc, sizeof(BP_RESOLUTION_INFO));    
  
   // The fields in the destination is the result of the AND of  
   //  bpInfoSrc.dwFields and dwFields.    
   bpResDest.dwFields = dwFields & bpResSrc.dwFields;    
  
   // Fill in the bp location information if the BPRESI_BPRESLOCATION  
   //  flag is set in BPRESI_FIELDS.    
   if (IsFlagSet(bpResDest.dwFields, BPRESI_BPRESLOCATION))    
   {    
      // Switch based on the BP_TYPE.     
      switch (bpResSrc.bpResLocation.bpType)    
      {    
         case BPT_CODE:    
         {    
            // AddRef the IDebugCodeContext2 of the BP_RESOLUTION_CODE structure.    
            bpResDest.bpResLocation.bpResLocation.bpresCode.pCodeContext->AddRef();    
            break;    
         }    
         case BPT_DATA:    
         {    
            // Copy the bstrDataExpr, bstrFunc, and bstrImage of the  
            // BP_RESOLUTION_DATA structure.    
            bpResDest.bpResLocation.bpResLocation.bpresData.bstrDataExpr =  
               SysAllocString(bpResSrc.bpResLocation.bpResLocation.bpresData.bstrDataExpr);    
            bpResDest.bpResLocation.bpResLocation.bpresData.bstrFunc =  
               SysAllocString(bpResSrc.bpResLocation.bpResLocation.bpresData.bstrFunc);    
            bpResSrc.bpResLocation.bpResLocation.bpresData.bstrImage =  
               SysAllocString(bpResSrc.bpResLocation.bpResLocation.bpresData.bstrImage);    
            break;    
         }    
         default:    
         {    
            assert(FALSE);    
            // Clear the BPRESI_BPRESLOCATION flag in the BPRESI_FIELDS  
            // of the destination BP_RESOLUTION_INFO.    
            ClearFlag(bpResDest.dwFields, BPRESI_BPRESLOCATION);    
            break;    
         }    
      }    
   }    
   // AddRef the IDebugProgram2 if the BPRESI_PROGRAM flag is set in BPRESI_FIELDS.  
   if (IsFlagSet(bpResDest.dwFields, BPRESI_PROGRAM))    
   {    
      bpResDest.pProgram->AddRef();    
   }    
   // AddRef the IDebugThread2 if the BPRESI_THREAD flag is set in BPRESI_FIELDS.  
   if (IsFlagSet(bpResDest.dwFields, BPRESI_THREAD))    
   {    
      bpResDest.pThread->AddRef();    
   }    
  
   return hr;    
}    
```  
  
## См. также  
 [IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md)   
 [BPRESI\_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md)   
 [BP\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)