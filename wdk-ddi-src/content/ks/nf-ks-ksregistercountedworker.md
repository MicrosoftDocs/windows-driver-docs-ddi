---
UID: NF:ks.KsRegisterCountedWorker
title: KsRegisterCountedWorker function (ks.h)
description: Handles clients registering for use of a thread.
old-location: stream\ksregistercountedworker.htm
tech.root: stream
ms.assetid: acec8050-44bd-4082-9875-d504135e1b9f
ms.date: 04/23/2018
keywords: ["KsRegisterCountedWorker function"]
ms.keywords: KsRegisterCountedWorker, KsRegisterCountedWorker function [Streaming Media Devices], ks/KsRegisterCountedWorker, ksfunc_2d4b1740-9b91-420d-81be-a56034445893.xml, stream.ksregistercountedworker
f1_keywords:
 - "ks/KsRegisterCountedWorker"
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
- KsRegisterCountedWorker
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsRegisterCountedWorker function


## -description


Handles clients registering for use of a thread.


## -parameters




### -param WorkQueueType [in]

Contains the priority of the work thread. This is normally one of the following: CriticalWorkQueue, DelayedWorkQueue, or HyperCriticalWorkQueue.


### -param CountedWorkItem [in]

Contains a pointer to the work queue item that will be queued as needed based on the current count value.


### -param Worker [out]

Contains the opaque context that must be used when scheduling a work item. Also contains the queue type, and is used to synchronize completion of work items.


## -returns



Returns STATUS_SUCCESS if a worker was initialized.




## -remarks



This must be matched by a corresponding <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksunregisterworker">KsUnregisterWorker</a> when thread use is completed. This function resembles <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksregisterworker">KsRegisterWorker</a>, with the addition of passing the work item that will always be queued. This is to be used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksincrementcountedworker">KsIncrementCountedWorker</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksdecrementcountedworker">KsDecrementCountedWorker</a> in order to minimize the number of work items queued, and reduce mutual exclusion code necessary in a work item needed to serialize access against multiple work item threads. The worker queue can still be used to queue other work items. This may only be called at PASSIVE_LEVEL.



