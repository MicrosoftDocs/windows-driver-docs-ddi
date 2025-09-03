---
UID: NF:wdm.KeRcuReadUnlock
tech.root: kernel
title: KeRcuReadUnlock function (wdm.h)
ms.date: 09/02/2025
targetos: Windows
description: The KeRcuReadUnlock function exits a RCU read-side critical section in the default RCU domain that was previously entered with KeRcuReadLock.
prerelease: false
ai-usage: ai-assisted
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: <= DISPATCH_LEVEL
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
 - KeRcuReadUnlock
f1_keywords:
 - KeRcuReadUnlock
 - wdm/KeRcuReadUnlock
dev_langs:
 - c++
helpviewer_keywords:
 - KeRcuReadUnlock
---

## -description

The **KeRcuReadUnlock** function exits a RCU (Read-Copy-Update) read-side critical section in the default RCU domain that was previously entered with [**KeRcuReadLock**](nf-wdm-kercureadlock.md).

## -remarks

This function unpins the calling thread from its processor, restores the original IRQL if needed, and performs any necessary grace period reporting to advance RCU synchronization.

**KeRcuReadUnlock** must be called to exit every RCU read-side critical section that was entered with [**KeRcuReadLock**](nf-wdm-kercureadlock.md). Calls must be properly nested (LIFO order) when using nested RCU read-side critical sections.

After calling **KeRcuReadUnlock**:

- The calling thread is no longer protected from RCU grace periods.
- RCU-protected data structures accessed during the critical section may become eligible for reclamation.
- The thread should not continue to access RCU-protected data using pointers obtained during the critical section.
- The thread is no longer pinned to its processor and may be scheduled on different processors.

This function can be called from any IRQL. The function automatically handles IRQL restoration; that is, if the original IRQL before the corresponding **KeRcuReadLock** was below DISPATCH_LEVEL, it will be restored to that level.

This function uses the default RCU domain, making it suitable for simple RCU use cases. For more complex scenarios requiring custom synchronization domains, use [**KeSrcuReadUnlock**](nf-wdm-kesrcureadunlock.md) with an explicit SRCU partition.

## -see-also

[**KeRcuReadLock**](nf-wdm-kercureadlock.md)

[**KeRcuSynchronize**](nf-wdm-kercusynchronize.md)

[**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md)

[**KeSrcuReadUnlock**](nf-wdm-kesrcureadunlock.md)

[**KeSrcuSynchronize**](nf-wdm-kesrcusynchronize.md)
