---
UID: NF:ks.KsCancelIo
title: KsCancelIo function (ks.h)
description: The KsCancelIo function cancels all IRPs on the specified cancel list. If an IRP on the list does not have a cancel routine, only the cancel bit is set in the IRP. The function can be called at IRQ level DISPATCH_LEVEL or lower.
old-location: stream\kscancelio.htm
tech.root: stream
ms.assetid: 082a63d5-5ba5-4cd3-aea3-0184317e1e96
ms.date: 04/23/2018
ms.keywords: KsCancelIo, KsCancelIo function [Streaming Media Devices], ks/KsCancelIo, ksfunc_135412c3-120f-4b19-ac05-da63ab6b1ddd.xml, stream.kscancelio
ms.topic: function
f1_keywords:
 - "ks/KsCancelIo"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsCancelIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsCancelIo function


## -description


The <b>KsCancelIo</b> function cancels all IRPs on the specified cancel list. If an IRP on the list does not have a cancel routine, only the cancel bit is set in the IRP. The function can be called at IRQ level DISPATCH_LEVEL or lower.


## -parameters




### -param QueueHead [in, out]

Specifies the head of a driver-maintained queue containing the IRP's to be canceled.


### -param SpinLock [in]

Points to a caller-allocated spin lock for queue access. A copy of this pointer is kept in the IRP's KSQUEUE_SPINLOCK_IRP_STORAGE(Irp) for use by the cancel routine, if necessary.


## -returns



None




## -remarks



<b>KsCancelIo </b>cancels all IRPs in a given driver-maintained queue. If the IRP has a cancel routine, the cancel routine is called. Otherwise, the cancel flag in the IRP is set to <b>TRUE</b>. The IRPs are not removed from the queue by this routine. It is the sole responsibility of the driver to ensure that the IRPs are removed either by the cancel routine specified in the IRP or by some other driver-supplied functionality.

If the IRP being canceled has a driver-supplied cancel routine, the cancel spin lock can be obtained from the IRP by calling KSQUEUE_SPINLOCK_IRP_STORAGE.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksaddirptocancelablequeue">KsAddIrpToCancelableQueue</a>
 

 

