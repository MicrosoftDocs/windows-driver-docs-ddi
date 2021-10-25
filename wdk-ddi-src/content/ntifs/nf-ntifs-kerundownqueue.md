---
UID: NF:ntifs.KeRundownQueue
title: KeRundownQueue function (ntifs.h)
description: The KeRundownQueue routine cleans up a queue object, flushing any queued entries.
old-location: ifsk\kerundownqueue.htm
tech.root: ifsk
ms.date: 08/30/2021
keywords: ["KeRundownQueue function"]
ms.keywords: KeRundownQueue, KeRundownQueue routine [Installable File System Drivers], ifsk.kerundownqueue, keref_d1ad3c47-a2e8-40d9-b59d-bcedd6e4314a.xml, ntifs/KeRundownQueue
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KeRundownQueue
 - ntifs/KeRundownQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeRundownQueue
---

# KeRundownQueue function

## -description

The **KeRundownQueue** routine cleans up a queue object, flushing any queued entries.

## -parameters

### -param Queue [in, out]

Pointer to an initialized queue object for which the caller provides resident storage in nonpaged pool.

## -returns

If the queue is empty, **KeRundownQueue** returns **NULL**; otherwise, it returns the address of the first entry in the queue.

## -remarks

File systems call **KeRundownQueue** to discard all entries from a queue before freeing or reusing the queue object.

If the queue object is to be reused, the caller must call [**KeInitializeQueue**](nf-ntifs-keinitializequeue.md) after calling **KeRundownQueue**, in order to reinitialize the queue object before reusing it.

**KeRundownQueue** returns no information about how many queued entries are discarded.

Starting in Windows 7, **KeRundownQueue** wakes any threads currently waiting on the queue object with STATUS_ABANDONED. After returning from this function, any future threads that try to wait on this queue will immediately fail with STATUS_ABANDONED.

Prior to Windows 7, **KeRundownQueue** did not wake waiting threads when the queue was rundown. To avoid the possibility of leaving threads waiting forever on these OS versions, **KeRundownQueue** should never be called for a queue if any threads are waiting on the queue object.

For more information about using driver-managed internal queues, see [Driver-Managed Queues](../_kernel/index.md#driver-managed-queues).

## -see-also

[**KeInitializeQueue**](nf-ntifs-keinitializequeue.md)

[**KeRemoveQueue**](nf-ntifs-keremovequeue.md)