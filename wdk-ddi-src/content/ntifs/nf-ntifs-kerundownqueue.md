---
UID: NF:ntifs.KeRundownQueue
title: KeRundownQueue function (ntifs.h)
description: The KeRundownQueue routine cleans up a queue object, flushing any queued entries.
old-location: ifsk\kerundownqueue.htm
tech.root: ifsk
ms.assetid: fc496af8-0b4b-4de4-8890-f2290970ced5
ms.date: 04/16/2018
keywords: ["KeRundownQueue function"]
ms.keywords: KeRundownQueue, KeRundownQueue routine [Installable File System Drivers], ifsk.kerundownqueue, keref_d1ad3c47-a2e8-40d9-b59d-bcedd6e4314a.xml, ntifs/KeRundownQueue
f1_keywords:
 - "ntifs/KeRundownQueue"
 - "KeRundownQueue"
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeRundownQueue
targetos: Windows
req.typenames: 
---

# KeRundownQueue function


## -description


The <b>KeRundownQueue</b> routine cleans up a queue object, flushing any queued entries. 


## -parameters




### -param Queue 
[in, out]
Pointer to an initialized queue object for which the caller provides resident storage in nonpaged pool.


## -returns



If the queue is empty, <b>KeRundownQueue</b> returns <b>NULL</b>; otherwise, it returns the address of the first entry in the queue. 




## -remarks



File systems call <b>KeRundownQueue</b> to discard all entries from a queue before freeing or reusing the queue object.

If the queue object is to be reused, the caller must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-keinitializequeue">KeInitializeQueue</a> after calling <b>KeRundownQueue</b>, in order to reinitialize the queue object before reusing it. 

<b>KeRundownQueue</b> returns no information about how many queued entries are discarded. 

<b>KeRundownQueue</b> should never be called for a queue if any threads are waiting on the queue object.

For more information about using driver-managed internal queues, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Driver-Managed Queues</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-keinitializequeue">KeInitializeQueue</a>
 

 

