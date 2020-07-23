---
UID: NF:ks.KsRemoveIrpFromCancelableQueue
title: KsRemoveIrpFromCancelableQueue function (ks.h)
description: The KsRemoveIrpFromCancelableQueue function pops the next noncanceled IRP from the specified queue that can be canceled and removes its cancel status.
old-location: stream\ksremoveirpfromcancelablequeue.htm
tech.root: stream
ms.assetid: 6bc23364-07c9-4a01-b475-e4620f62a674
ms.date: 04/23/2018
keywords: ["KsRemoveIrpFromCancelableQueue function"]
ms.keywords: KsRemoveIrpFromCancelableQueue, KsRemoveIrpFromCancelableQueue function [Streaming Media Devices], ks/KsRemoveIrpFromCancelableQueue, ksfunc_35dd895b-1a0b-40a2-bc84-cdc2844bd30f.xml, stream.ksremoveirpfromcancelablequeue
f1_keywords:
 - "ks/KsRemoveIrpFromCancelableQueue"
 - "KsRemoveIrpFromCancelableQueue"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsRemoveIrpFromCancelableQueue
targetos: Windows
req.typenames: 
---

# KsRemoveIrpFromCancelableQueue function

## -description

The **KsRemoveIrpFromCancelableQueue** function pops the next noncanceled IRP from the specified queue that can be canceled and removes its cancel status. The function searches the list until an IRP is found that has a cancel routine or until the end of the list is reached. The function minimizes the use of the cancel spin lock by using the provided spin lock to synchronize access in most cases. The function may be called at IRQ level DISPATCH_LEVEL or lower.

## -parameters

### -param QueueHead [in, out]

Points to the head of the queue from which to remove the IRP.

### -param SpinLock [in]

Points to driver's spin lock for queue access.

### -param ListLocation [in]

Indicates whether this IRP should come from the beginning or end of the queue.

### -param RemovalOperation [in]

Specifies whether the IRP is removed from the list or just acquired by setting the cancel function to **NULL**. If it is only acquired, the IRP must be later released with **KsReleaseIrpOnCancelableQueue** or completely removed with **KsRemoveSpecificIrpFromCancelableQueue**.

## -returns

The **KsRemoveIrpFromCancelableQueue** function returns the next noncanceled IRP on the list, or it returns **NULL** if none is found or if an IRP that has not already been acquired cannot be found.

## -remarks

These enumerations are used in the previous parameters to control where the IRP is removed from and how.

```cpp
typedef enum {
    KsListEntryTail,
    KsListEntryHead
} KSLIST_ENTRY_LOCATION;

typedef enum {
    KsAcquireOnly,
    KsAcquireAndRemove
} KSIRP_REMOVAL_OPERATION;
```

## -see-also

[KsReleaseIrpOnCancelableQueue](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksreleaseirponcancelablequeue)

[KsRemoveSpecificIrpFromCancelableQueue](https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksremovespecificirpfromcancelablequeue)
