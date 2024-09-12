---
UID: NF:wdm.KeAcquireInStackQueuedSpinLock
tech.root: kernel
title: KeAcquireInStackQueuedSpinLock
ms.date: 07/29/2024
targetos: Windows
description: Learn more about the KeAcquireInStackQueuedSpinLock routine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: IRQL <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DLLExport
api_location:
 - wdm.h
api_name:
 - KeAcquireInStackQueuedSpinLock
f1_keywords:
 - KeAcquireInStackQueuedSpinLock
 - wdm/KeAcquireInStackQueuedSpinLock
dev_langs:
 - c++
helpviewer_keywords:
 - KeAcquireInStackQueuedSpinLock
---

## -description

The **KeAcquireInStackQueuedSpinLock** routine acquires a queued spin lock.

## -parameters

### -param SpinLock

[in, out] Specifies the spin lock to acquire. This parameter must have been initialized with [**KeInitializeSpinLock**](nf-wdm-keinitializespinlock.md).

### -param LockHandle

[out] A pointer to a caller-supplied [**KLOCK_QUEUE_HANDLE**](/windows-hardware/drivers/kernel/eprocess) variable that the routine can use to return the spin lock queue handle. The caller passes this value to [**KeReleaseInStackQueuedSpinLock**](nf-wdm-kereleaseinstackqueuedspinlock.md) when releasing the lock. Drivers should normally allocate the structure on the stack each time they acquire the lock. A driver should not use the same KLOCK_QUEUE_HANDLE from multiple calling sites.

## -remarks

**KeAcquireInStackQueuedSpinLock** acquires a spin lock as a *queued spin lock*. For more information, see [Queued Spin Locks](/windows-hardware/drivers/kernel/queued-spin-locks). The caller releases the spin lock by calling the [**KeReleaseInStackQueuedSpinLock**](nf-wdm-kereleaseinstackqueuedspinlock.md) routine.

Like ordinary spin locks, queued spin locks must only be used in very special circumstances. For a description of when to use spin locks, see [**KeAcquireSpinLock**](nf-wdm-keacquirespinlock.md).

This routine raises the IRQL level to DISPATCH_LEVEL when acquiring the spin lock. If the caller is guaranteed to already be running at DISPATCH_LEVEL, it is more efficient to call [**KeAcquireInStackQueuedSpinLockAtDpcLevel**](nf-wdm-keacquireinstackqueuedspinlockatdpclevel.md).

The call to **KeReleaseInStackQueuedSpinLock** that releases the spin lock must occur at IRQL = DISPATCH_LEVEL. This call restores the original IRQL that the operating system saved at the beginning of the **KeAcquireInStackQueuedSpinLock** call. If a driver acquires multiple queued spin locks in series, it must release them in reverse order to properly restore the original IRQL.

Drivers must not combine calls to **KeAcquireSpinLock** and **KeAcquireInStackQueuedSpinLock** on the same spin lock. A spin lock must always be acquired or released as either a queued spin lock, or as an ordinary spin lock.

## -see-also

[**KLOCK_QUEUE_HANDLE**](/windows-hardware/drivers/kernel/eprocess)

[**KeAcquireInStackQueuedSpinLockAtDpcLevel**](nf-wdm-keacquireinstackqueuedspinlockatdpclevel.md)

[**KeAcquireSpinLock**](nf-wdm-keacquirespinlock.md)

[**KeInitializeSpinLock**](nf-wdm-keinitializespinlock.md)

[**KeReleaseInStackQueuedSpinLock**](nf-wdm-kereleaseinstackqueuedspinlock.md)
