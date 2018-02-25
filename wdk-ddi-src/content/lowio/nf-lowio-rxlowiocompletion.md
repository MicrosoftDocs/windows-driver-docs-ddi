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
ms.keywords: ",  , C, I, L, R, RxLowIoCompletion, RxLowIoCompletion routine [Installable File System Drivers], e, i, ifsk.rxlowiocompletion, l, lowio/RxLowIoCompletion, m, n, o, p, rxref_9a8f198a-0177-42f5-9039-3f5d6a3fa14d.xml, t, w, x"
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	lowio.h
apiname:
-	RxLowIoCompletion
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# RxLowIoCompletion function


## -description


<b>RxLowIoCompletion</b> must be called by the network mini-redirector low I/O routines when they complete, if the low I/O routines have initially returned STATUS_PENDING.


## -syntax


````
NTSTATUS RxLowIoCompletion(
   PRX_CONTEXT RxContext
);
````


## -parameters




### -param RxContext

A pointer to the RX_CONTEXT structure for this IRP.


## -returns



<b>RxLowIoCompletion</b>
      returns different values depending on whether the <i>RxContext</i> parameter indicates this is synchronous or asynchornous I/O.

If the <i>RxContext</i> parameter indicates this is synchronous I/O, then <b>RxLowIoCompletion</b> returns STATUS_MORE_PROCESSING_REQUIRED. 

If the <i>RxContext</i> parameter indicates this is asynchronous I/O, then <b>RxLowIoCompletion</b> will try to call the <b>LowIoContext.CompletionRoutine</b> member of the RX_CONTEXT. The completion routine will only be called if the <b>LowIoContext.Flags</b>member indicates that the completion routine can be called at DPC level and the current IRQL is less than dispatch level. In this case, the return value is the result returned by the completion routine. If these conditions are not met, then <b>RxLowIoCompletion</b> returns STATUS_MORE_PROCESSING_REQUIRED. 




## -see-also

<a href="..\rxcontx\ns-rxcontx-_rx_context.md">RX_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554591">RxNewMapUserBuffer</a>



<a href="..\lowio\nf-lowio-rxlowiogetbufferaddress.md">RxLowIoGetBufferAddress</a>



<a href="..\rxprocs\nf-rxprocs-rxmapsystembuffer.md">RxMapSystemBuffer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxLowIoCompletion routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

