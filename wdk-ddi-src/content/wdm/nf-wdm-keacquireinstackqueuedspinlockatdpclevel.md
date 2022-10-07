---
UID: NF:wdm.KeAcquireInStackQueuedSpinLockAtDpcLevel
tech.root: kernel
title: KeAcquireInStackQueuedSpinLockAtDpcLevel
ms.date: 10/05/2022
targetos: Windows
description: Learn more about the KeAcquireInStackQueuedSpinLockAtDpcLevel routine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: >= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows XP
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
 - KeAcquireInStackQueuedSpinLockAtDpcLevel
f1_keywords:
 - KeAcquireInStackQueuedSpinLockAtDpcLevel
 - wdm/KeAcquireInStackQueuedSpinLockAtDpcLevel
dev_langs:
 - c++
helpviewer_keywords:
 - KeAcquireInStackQueuedSpinLockAtDpcLevel
---

## -description

The **KeAcquireInStackQueuedSpinLockAtDpcLevel** routine acquires a queued spin lock when the caller is already running at IRQL \>= DISPATCH\_LEVEL.

## -parameters

### -param SpinLock

[in, out] Specifies the spin lock to acquire. This parameter must have been initialized by a call to the [**KeInitializeSpinLock**](nf-wdm-keinitializespinlock.md) routine.

### -param LockHandle

[out] Pointer to a caller-supplied [**KLOCK\_QUEUE\_HANDLE**](/windows-hardware/drivers/kernel/eprocess) structure that the routine can use to return the spin lock queue handle. To release the lock, the caller passes this value to the [**KeReleaseInStackQueuedSpinLockFromDpcLevel**](nf-wdm-kereleaseinstackqueuedspinlockfromdpclevel.md) routine.

## -remarks

For a driver running at IRQL \>= DISPATCH\_LEVEL, **KeAcquireInStackQueuedSpinLockAtDpcLevel** acquires a spin lock as a *queued spin lock*. For more information, see [Queued Spin Locks](/windows-hardware/drivers/kernel/queued-spin-locks). To release the spin lock, call the [**KeReleaseInStackQueuedSpinLockFromDpcLevel**](nf-wdm-kereleaseinstackqueuedspinlockfromdpclevel.md) routine.

Drivers that are already running at an IRQL \>= DISPATCH\_LEVEL can call this routine to acquire the queued spin lock more quickly. Otherwise, use the [**KeAcquireInStackQueuedSpinLock**](nf-wdm-keacquireinstackqueuedspinlock.md) routine to acquire the spin lock.

For a driver that is running at IRQL \> DISPATCH\_LEVEL, this routine acquires the lock without modifying the current IRQL. For a driver that is running at IRQL = DISPATCH\_LEVEL, this routine improves performance by acquiring the lock without first setting the IRQL to DISPATCH\_LEVEL, which, in this case, would be a redundant operation.

Like ordinary spin locks, queued spin locks must only be used in very special circumstances. For a description of when to use spin locks, see [**KeAcquireSpinLock**](nf-wdm-keacquirespinlock.md).

Drivers must not combine calls to [**KeAcquireSpinLock**](nf-wdm-keacquirespinlock.md) and **KeAcquireInStackQueuedSpinLock** on the same spin lock. A spin lock must always be acquired or released either as a queued spin lock, or as an ordinary spin lock.

## -see-also

[**KLOCK\_QUEUE\_HANDLE**](/windows-hardware/drivers/kernel/eprocess)

[**KeAcquireSpinLock**](nf-wdm-keacquirespinlock.md)

[**KeAcquireInStackQueuedSpinLock**](nf-wdm-keacquireinstackqueuedspinlock.md)

[**KeInitializeSpinLock**](nf-wdm-keinitializespinlock.md)

[**KeReleaseInStackQueuedSpinLockFromDpcLevel**](nf-wdm-kereleaseinstackqueuedspinlockfromdpclevel.md)
