---
UID: NF:ntifs.KeRemoveQueue
title: KeRemoveQueue function (ntifs.h)
description: Learn more about the KeRemoveQueue function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["KeRemoveQueue function"]
ms.keywords: KeRemoveQueue, KeRemoveQueue routine [Installable File System Drivers], ifsk.keremovequeue, keref_99014b0b-5ca1-4cda-8422-fc3819f42d8b.xml, ntifs/KeRemoveQueue
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
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
 - KeRemoveQueue
 - ntifs/KeRemoveQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeRemoveQueue
---

# KeRemoveQueue function

## -description

The **KeRemoveQueue** routine gives the calling thread a pointer to a dequeued entry from the given queue object or allows the caller to wait, up to an optional timeout interval, on the queue object.

## -parameters

### -param Queue [in, out]

Pointer to an initialized queue object for which the caller provides resident storage in nonpaged pool.

### -param WaitMode [in]

The processor mode in which the caller is waiting, which can be either **KernelMode** or **UserMode**. If anything on its stack might be accessed at IRQL >= DISPATCH_LEVEL, the caller must specify **KernelMode**.

### -param Timeout [in, optional]

Pointer to a variable that specifies the absolute or relative time, in units of 100 nanoseconds, at which the wait is to expire. If the value of **Timeout** is negative, the expiration time is relative to the current system time; otherwise, it is absolute. Absolute expiration times track any changes in system time; relative expiration times are not affected by system time changes. This pointer can be NULL.

## -returns

**KeRemoveQueue** returns one of the following:

* A pointer to a dequeued entry from the given queue object, if one is available.
* STATUS_TIMEOUT, if the given Timeout interval expired before an entry became available
* STATUS_USER_APC, if a user-mode APC was delivered in the context of the calling thread
* STATUS_ABANDONED, if the queue has been run down

## -remarks

Callers of **KeRemoveQueue** should test whether its return value is STATUS_TIMEOUT or STATUS_USER_APC before accessing any entry members. Testing the return value of **KeRemoveQueue** against **NULL** is a programming error.

Specifying a zero value for ***Timeout** indicates the caller's unwillingness to wait for an entry if the queue is currently empty. Specifying a **NULL****Timeout** pointer indicates the caller's willingness to wait indefinitely for an entry.

If the **WaitMode** parameter is **UserMode**, the kernel stack can be swapped out during the wait. Consequently, a caller must never attempt to pass parameters on the stack when calling **KeRemoveQueue** with **WaitMode** set to **UserMode**.

Specifying **WaitMode** as **KernelMode** in a call to **KeRemoveQueue** prevents the calling thread's kernel stack from being swapped out, as well as preventing the delivery of user-mode asynchronous procedure calls (APC). It does not prevent the delivery of kernel-mode APCs, such as those used by the I/O Manager to complete IRPs, when a thread calls **KeRemoveQueue** from IRQL PASSIVE_LEVEL. Delivery of such a kernel-mode APC does not prevent the calling thread from waiting on the queue object nor from being dispatched for execution with an entry after the kernel APC has run.

For more information about using driver-managed internal queues, see [Driver-Managed Queues](/windows-hardware/drivers/ddi/_kernel/#driver-managed-queues).

## -see-also

[**KeInsertHeadQueue**](nf-ntifs-keinsertheadqueue.md)

[**KeInsertQueue**](nf-ntifs-keinsertqueue.md)
