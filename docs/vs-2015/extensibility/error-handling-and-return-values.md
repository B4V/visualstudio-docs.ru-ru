---
title: Обработка ошибок и возвращаемые значения | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors [Visual Studio SDK], handling
- error handling
- return values
ms.assetid: b2d9079d-39a6-438a-8010-290056694b5c
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 315315e925eecd45b1c001531f5ebb6be207b2e7
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49306856"
---
# <a name="error-handling-and-return-values"></a>Обработка ошибок и возвращаемые значения
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Пакеты VSPackage и COM используют ту же архитектуру для ошибки. `SetErrorInfo` И `GetErrorInfo` функции являются частью интерфейс (API) Win32. Любой пакет VSPackage в интегрированной среде разработки (IDE) можно вызвать эти глобальные API-интерфейсов Win32 для записи подробных сведений об ошибках информации при получении уведомление об ошибке. [!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)] Предоставляет сборок взаимодействия для управления сведений об ошибке.  
  
## <a name="interop-methods"></a>Методы взаимодействия  
 Для удобства, интегрированная среда разработки предоставляет метод, <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A>, чтобы использовать вместо того чтобы вызывать API-интерфейсов Win32. В управляемом коде используйте <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A>. При возникновении ошибки `HRESULT` приходит на уровне, где должен отображаться сообщение об ошибке (это часто объект реализации <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> обработчик команд), интегрированной среды разработки используется другой метод <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A>, чтобы отобразить окно сообщения. В управляемом коде используйте <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> метод.  
  
 Как разработчик VSPackage, объектов COM обычно реализуют `ISupportErrorInfo`. `ISupportErrorInfo` Интерфейс гарантирует, что сведения об ошибке можно перейти по вертикали в цепочке вызовов. Объекты, которые могут использоваться между процессами или между потоками, должны поддерживать `ISupportErrorInfo` чтобы убедиться, что сведения об ошибке правильно маршалируется обратно вызывающему.  
  
 Все объекты, связанные с VSPackages и, которые участвуют в расширении возможностей интегрированной среды разработки, включая фабрики редактора, редакторы, иерархии и предоставляемые службы, должны поддерживать сведения об ошибке. Хотя эти объекты VSPackage для реализации интегрированной среды разработки не требует `ISupportErrorInfo`, мы рекомендуем всегда.  
  
 IDE отвечает за reporting сведения об ошибке и его отображения пользователю [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] всякий раз, когда `HRESULT` распространяется в интегрированную среду разработки. IDE также является механизм для создания `ErrorInfo` объектов.  
  
## <a name="general-guidelines"></a>Общие рекомендации  
 Можно использовать <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> и <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> методы задания и сообщать об ошибках, которые являются внутренними для вашей реализации VSPackage. Тем не менее как правило, придерживайтесь следующих рекомендаций для обработки сообщений об ошибках в VSPackage.  
  
-   Реализуйте `ISupportErrorInfo` в объектах VSPackage COM.  
  
-   Создать механизм, который вызывает для отчетов об ошибках <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> метод в объекты, реализующие <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
-   Разрешить отображение ошибок, пользователей с помощью интегрированной среды разработки <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> метод.  
  
## <a name="error-information-in-the-ide"></a>Сведения об ошибке в интегрированной среде разработки  
 Следующие правила определяют способ обработки сведений об ошибках в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] интегрированной среды разработки:  
  
-   Как стратегии безопасности, чтобы гарантировать, что устаревшим ошибка сведения не входят в отчет для пользователей, функции, вызывающие <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> необходимо сначала вызвать метод <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> метод. Передайте `null` снимите кэшированный ошибки сообщения, прежде чем что-либо вызове, задать новые сведения об ошибке.  
  
-   Разрешены только функции, которые непосредственно не передают сообщения об ошибках для вызова <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> метод, если они возвращают ошибку `HRESULT`. Можно очистить `ErrorInfo` запись на функцию или при возврате <xref:Microsoft.VisualStudio.VSConstants.S_OK>. Единственное исключение для этого правила — если вызов возвращает ошибку `HRESULT` из которой получающая сторона можно явно восстановить или игнорировать.  
  
-   Любая сторона, которая явно не обрабатывает ошибку `HRESULT` необходимо вызвать <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> метод с <xref:Microsoft.VisualStudio.VSConstants.S_OK>. В противном случае `ErrorInfo` объект может быть случайно использовано, когда другой стороной приводит к ошибке, не предоставляя собственные `ErrorInfo`.  
  
-   Все методы, которые происходят ошибки `HRESULT` рекомендуется вызвать <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> метод, чтобы предоставить сведения об ошибке. Если возвращенный `HRESULT` является специальной `FACILITY_ITF` error, то метод должен предоставить подходящий `ErrorInfo`объекта. Если стандартная системная ошибка возвращена следующая ошибка (например, <xref:Microsoft.VisualStudio.VSConstants.E_OUTOFMEMORY>, <xref:Microsoft.VisualStudio.VSConstants.E_ABORT>, <xref:Microsoft.VisualStudio.VSConstants.E_INVALIDARG>, <xref:Microsoft.VisualStudio.VSConstants.E_UNEXPECTED>и т. д.) это допустимо для возврата кода ошибки без явного вызова <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> метод. Как защитного кодирования стратегия, при ошибка `HRESULT` (включая системные ошибки), следует всегда вызывать <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SetErrorInfo%2A> метод, с помощью `ErrorInfo` описывающих сбой более подробно, или `null`.  
  
-   Все функции, возвращающие ошибку, исходящих от другого вызова необходимо передать на сведения, которые были получены от отказавшего вызывают из `HRESULT` без изменения `ErrorInfo` объекта.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [SetErrorInfo (автоматизации компонентов)](http://msdn.microsoft.com/en-us/8eaacfac-fc37-4eaa-870b-10b99d598d66)   
 [GetErrorInfo](http://msdn.microsoft.com/en-us/03317526-8c4f-4173-bc10-110c8112676a)   
 [Интерфейс ISupportErrorInfo](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32)

