---
UID: NF:ks.KsQueueWorkItem
title: KsQueueWorkItem function (ks.h)
description: The KsQueueWorkItem function queues the specified work item with a worker previous created by the KsRegisterWorker function.
old-location: stream\ksqueueworkitem.htm
tech.root: stream
ms.assetid: a700979e-aee4-4bce-8f98-b44b864fbb43
ms.date: 04/23/2018
keywords: ["KsQueueWorkItem function"]
ms.keywords: KsQueueWorkItem, KsQueueWorkItem function [Streaming Media Devices], ks/KsQueueWorkItem, ksfunc_abb711a0-0862-4d91-b2e1-3af290f1112f.xml, stream.ksqueueworkitem
f1_keywords:
 - "ks/KsQueueWorkItem"
 - "KsQueueWorkItem"
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
- KsQueueWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsQueueWorkItem function


## -description


The <b>KsQueueWorkItem</b> function queues the specified work item with a worker previous created by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksregisterworker">KsRegisterWorker</a> function.


## -parameters




### -param Worker [in]

Specifies the previously allocated worker.


### -param WorkItem [in]

Specifies the initialized work item to queue. This work item is only associated with the worker as long as the worker is on a queue. The work item must have been initialized by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a>.


## -returns



The <b>KsQueueWorkItem</b> function returns STATUS_SUCCESS if the work item was queued, or if unsuccessful the function returns an error when attempting to create a new worker if no threads are currently available.




## -remarks



The worker can only be on a queue in one place, so subsequent queuing of the worker must wait until the work item has begun executing. This function may be called at <b>DISPATCH_LEVEL</b>.



