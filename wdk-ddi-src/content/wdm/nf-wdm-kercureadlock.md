---
UID: NF:wdm.KeRcuReadLock
tech.root: kernel
title: KeRcuReadLock function (wdm.h)
ms.date: 09/02/2025
targetos: Windows
description: The KeRcuReadLock function enters a RCU read-side critical section in the default RCU domain, pinning the current thread to its processor and preventing preemption.
prerelease: false
ai-usage: ai-assisted
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: Any level (See Remarks)
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: Windows Server 2025
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - KeRcuReadLock
f1_keywords:
 - KeRcuReadLock
 - wdm/KeRcuReadLock
dev_langs:
 - c++
helpviewer_keywords:
 - KeRcuReadLock
---

## -description

The **KeRcuReadLock** function enters a RCU (Read-Copy-Update) read-side critical section in the default RCU domain. This function pins the calling thread to its current processor and prevents it from being preempted by the scheduler.

## -remarks

**KeRcuReadLock** provides low-cost synchronization for reading shared data structures without traditional locking overhead. It only accesses data local to the current CPU, making it extremely efficient.

RCU read-side critical sections allow multiple threads to concurrently access shared data structures while ensuring that writers can safely update the data using RCU protocols. RCU read-side critical sections can be nested.

**KeRcuReadLock** must always be paired with a corresponding call to [**KeRcuReadUnlock**](nf-wdm-kercureadunlock.md).

This function cannot fail and always succeeds.

Within a RCU read-side critical section:

- The calling thread is guaranteed that RCU-protected data structures won't be reclaimed.
- Multiple readers can access the same data concurrently without blocking each other.
- The thread should access only RCU-protected data structures using appropriate RCU dereference primitives.
- The thread must not perform operations that could cause extended delays.

This function can be called from any IRQL. If it's called below DISPATCH_LEVEL, the function automatically raises IRQL to DISPATCH_LEVEL. The original IRQL is restored when the corresponding [**KeRcuReadUnlock**](nf-wdm-kercureadunlock.md) is called

The calling thread is pinned to its current processor to maintain RCU semantics. If the processor is marked as idle, the function adjusts the idle state counters appropriately. The scheduler is prevented from preempting the thread while in the critical section.

The function uses the default RCU domain, making it suitable for simple RCU use cases. For more complex scenarios requiring custom synchronization domains, use [**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md) with an explicit SRCU partition.

## -see-also

[**KeRcuReadUnlock**](nf-wdm-kercureadunlock.md)

[**KeRcuSynchronize**](nf-wdm-kercusynchronize.md)

[**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md)

[**KeSrcuReadUnlock**](nf-wdm-kesrcureadunlock.md)

[**KeSrcuAllocate**](nf-wdm-kesrcuallocate.md)
