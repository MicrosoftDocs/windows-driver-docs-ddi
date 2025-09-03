---
UID: NF:wdm.KeSrcuReadUnlock
tech.root: kernel
title: KeSrcuReadUnlock function (wdm.h)
ms.date: 09/02/2025
targetos: Windows
description: The KeSrcuReadUnlock routine exits a read-side critical section for a Sleepable Read-Copy-Update (SRCU) partition.
prerelease: false
ai-usage: ai-assisted
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: NtosKrnl.exe
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.irql: Any level (see Remarks)
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeSrcuReadUnlock
f1_keywords:
 - KeSrcuReadUnlock
 - wdm/KeSrcuReadUnlock
dev_langs:
 - c++
helpviewer_keywords:
 - KeSrcuReadUnlock
---

## -description

The **KeSrcuReadUnlock** routine exits a read-side RCU critical section of a specified Sleepable Read-Copy-Update (SRCU) partition.

## -parameters

### -param Rcu [in]

A pointer to the SRCU instance that was used in the corresponding [**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md) call.

### -param Lock [in]

A pointer to the [**KE_SRCU_LOCK**](ns-wdm-ke_srcu_lock.md) structure that was filled by the corresponding [**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md) call.

## -remarks

**KeSrcuReadUnlock** exits a read-side critical section that was entered with [**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md). This function must be called in the same thread that called the corresponding [**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md).

This function can be called at any IRQL when the thread is still on the same processor. If the thread migrated to a different processor, the maximum effective IRQL is DISPATCH_LEVEL due to inter-processor interrupt (IPI) requirements.

This function can be called with interrupts disabled.

If the calling thread migrated to a different processor since calling [**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md), this function will:

1. Detect the processor change.
2. Send an inter-processor interrupt (IPI) to the original processor.
3. Complete the unlock operation remotely on the original processor.

After this call, the protected data should no longer be accessed.

## -see-also

[**KE_SRCU_LOCK**](ns-wdm-ke_srcu_lock.md)

[**KeSrcuAllocate**](nf-wdm-kesrcuallocate.md)

[**KeSrcuFree**](nf-wdm-kesrcufree.md)

[**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md)

[**KeSrcuSynchronize**](nf-wdm-kesrcusynchronize.md)
