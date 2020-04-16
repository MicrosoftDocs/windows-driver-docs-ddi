---
UID: NC:ks.PFNKSSTREAMPOINTER
title: PFNKSSTREAMPOINTER (ks.h)
description: AVStream calls a minidriver's AVStrMiniCancelCallback routine when the IRP that is associated with a cloned stream pointer is canceled. This routine is optional.
old-location: stream\avstrminicancelcallback.htm
tech.root: stream
ms.assetid: 4c95ccb6-c796-4bb2-b344-aa8eea28e131
ms.date: 04/23/2018
keywords: ["PFNKSSTREAMPOINTER callback function"]
ms.keywords: AVStrMiniCancelCallback, AVStrMiniCancelCallback routine [Streaming Media Devices], PFNKSSTREAMPOINTER, avstclbk_b23a511e-6e6a-4eaf-a64e-707983534d6f.xml, ks/AVStrMiniCancelCallback, stream.avstrminicancelcallback
f1_keywords:
 - "ks/AVStrMiniCancelCallback"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ks.h
api_name:
- AVStrMiniCancelCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSSTREAMPOINTER callback function


## -description


AVStream calls a minidriver's <i>AVStrMiniCancelCallback</i> routine when the IRP that is associated with a cloned stream pointer is canceled. This routine is optional.


## -parameters




### -param StreamPointer [in]

A pointer to the clone <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> that is associated with the IRP that was canceled. <i>StreamPointer</i> was created by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ks-ksstreampointerclone">KsStreamPointerClone</a>.


## -remarks



The minidriver specifies this routine's address in the <i>CancelCallback</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ks-ksstreampointerclone">KsStreamPointerClone</a>.

In <i>AVStrMiniCancelCallback</i>, the minidriver should set all references to the clone pointer to <b>NULL</b>.

In addition, the minidriver should remove any context information that is related to the clone pointer, and notify hardware about the cancellation.

Finally, the minidriver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointerdelete">KsStreamPointerDelete</a> to delete the clone and the context associated with it. If the minidriver does not delete the clone, the IRP will retain a reference count and not complete, possibly causing related applications to crash.

<i>AVStrMiniCancelCallback</i> is called with the queue's spin lock held, hence at DISPATCH_LEVEL. Accordingly, the callback routine cannot perform queue manipulation or call functions that acquire a mutex.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ks-ksstreampointerclone">KsStreamPointerClone</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksstreampointerdelete">KsStreamPointerDelete</a>
 

 

