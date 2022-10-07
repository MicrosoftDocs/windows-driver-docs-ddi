---
UID: NF:wdm.KeAcquireInStackQueuedSpinLockForDpc
tech.root: kernel
title: KeAcquireInStackQueuedSpinLockForDpc
ms.date: 10/05/2022
targetos: Windows
description: Learn more about the KeAcquireInStackQueuedSpinLockForDpc routine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows Vista
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
 - KeAcquireInStackQueuedSpinLockForDpc
f1_keywords:
 - KeAcquireInStackQueuedSpinLockForDpc
 - wdm/KeAcquireInStackQueuedSpinLockForDpc
dev_langs:
 - c++
helpviewer_keywords:
 - KeAcquireInStackQueuedSpinLockForDpc
---

## -description

The **KeAcquireInStackQueuedSpinLockForDpc** routine acquires a queued spin lock for a threaded DPC.

## -parameters

### -param SpinLock

[in, out] Pointer to the spin lock to acquire as a queued spin lock. You must have already initialized the spin lock by calling [**KeInitializeSpinLock**](nf-wdm-keinitializespinlock.md).

### -param LockHandle

[out] Pointer to a [**KLOCK\_QUEUE\_HANDLE**](/windows-hardware/drivers/kernel/eprocess) structure that receives the lock queue handle. Pass this value to the [**KeReleaseInStackQueuedSpinLockForDpc**](nf-wdm-kereleaseinstackqueuedspinlockfordpc.md) routine when you release the queued spin lock.

## -remarks

A [*CustomThreadedDpc*](/windows-hardware/drivers/kernel/introduction-to-threaded-dpcs) routine can use **KeAcquireInStackQueuedSpinLockForDpc** to acquire a queued spin lock. If *CustomThreadedDpc* is executing at IRQL = PASSIVE\_LEVEL, **KeAcquireInStackQueuedSpinLockForDpc** raises the current IRQL to DISPATCH\_LEVEL. If *CustomThreadedDpc* is already executing at IRQL = DISPATCH\_LEVEL, **KeAcquireInStackQueuedSpinLockForDpc** does not change the current IRQL.

For more information about queued spin locks, see [Queued Spin Locks](/windows-hardware/drivers/kernel/queued-spin-locks).

Call **KeReleaseInStackQueuedSpinLockForDpc** to release the spin lock that **KeAcquireInStackQueuedSpinLockForDpc** acquired.

## -see-also

[*CustomThreadedDpc*](/windows-hardware/drivers/kernel/introduction-to-threaded-dpcs)

[**KLOCK\_QUEUE\_HANDLE**](/windows-hardware/drivers/kernel/eprocess)

[**KeInitializeSpinLock**](nf-wdm-keinitializespinlock.md)

[**KeReleaseInStackQueuedSpinLockForDpc**](nf-wdm-kereleaseinstackqueuedspinlockfordpc.md)
