---
UID: NF:lowio.RxLowIoCompletion
title: RxLowIoCompletion function
author: windows-driver-content
description: RxLowIoCompletion must be called by the network mini-redirector low I/O routines when they complete, if the low I/O routines have initially returned STATUS_PENDING.
old-location: ifsk\rxlowiocompletion.htm
old-project: ifsk
ms.assetid: d9018a68-e72c-4149-a6a5-095654d0363c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxLowIoCompletion, RxLowIoCompletion routine [Installable File System Drivers], ifsk.rxlowiocompletion, lowio/RxLowIoCompletion, rxref_9a8f198a-0177-42f5-9039-3f5d6a3fa14d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: lowio.h
req.include-header: Lowio.h, Rxcontx.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	lowio.h
api_name:
-	RxLowIoCompletion
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# RxLowIoCompletion function


## -description


<b>RxLowIoCompletion</b> must be called by the network mini-redirector low I/O routines when they complete, if the low I/O routines have initially returned STATUS_PENDING.


## -parameters




### -param RxContext

A pointer to the RX_CONTEXT structure for this IRP.


## -returns



<b>RxLowIoCompletion</b>
      returns different values depending on whether the <i>RxContext</i> parameter indicates this is synchronous or asynchornous I/O.

If the <i>RxContext</i> parameter indicates this is synchronous I/O, then <b>RxLowIoCompletion</b> returns STATUS_MORE_PROCESSING_REQUIRED. 

If the <i>RxContext</i> parameter indicates this is asynchronous I/O, then <b>RxLowIoCompletion</b> will try to call the <b>LowIoContext.CompletionRoutine</b> member of the RX_CONTEXT. The completion routine will only be called if the <b>LowIoContext.Flags</b>member indicates that the completion routine can be called at DPC level and the current IRQL is less than dispatch level. In this case, the return value is the result returned by the completion routine. If these conditions are not met, then <b>RxLowIoCompletion</b> returns STATUS_MORE_PROCESSING_REQUIRED. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554751">RX_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554529">RxLowIoGetBufferAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554549">RxMapSystemBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554591">RxNewMapUserBuffer</a>
 

 

