---
UID: NF:wdm.KeAcquireSpinLockForDpc
tech.root: kernel
title: KeAcquireSpinLockForDpc
ms.date: 10/05/2022
targetos: Windows
description: Learn more about the KeAcquireSpinLockForDpc routine.
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
 - KeAcquireSpinLockForDpc
f1_keywords:
 - KeAcquireSpinLockForDpc
 - wdm/KeAcquireSpinLockForDpc
dev_langs:
 - c++
helpviewer_keywords:
 - KeAcquireSpinLockForDpc
---

## -description

The **KeAcquireSpinLockForDpc** routine acquires a threaded DPC spin lock.

## -parameters

### -param SpinLock

[in, out] Pointer to the spin lock to acquire. You must have already initialized the spin lock by calling [**KeInitializeSpinLock**](nf-wdm-keinitializespinlock.md).

## -returns

**KeAcquireSpinLockForDpc** returns the current IRQL at the time the routine is called. Pass this value to [**KeReleaseSpinLockForDpc**](nf-wdm-kereleasespinlockfordpc.md) when you release the spin lock.

## -remarks

A [*CustomThreadedDpc*](/windows-hardware/drivers/kernel/introduction-to-threaded-dpcs) routine can call **KeAcquireSpinLockForDpc** to acquire a spin lock. If *CustomThreadedDpc* is executing at IRQL = PASSIVE\_LEVEL, **KeAcquireSpinLockForDpc** raises the current IRQL to DISPATCH\_LEVEL. If *CustomThreadedDpc* is already executing at IRQL = DISPATCH\_LEVEL, **KeAcquireSpinLockForDpc** does not change the current IRQL.

Call [**KeReleaseSpinLockForDpc**](nf-wdm-kereleasespinlockfordpc.md) to release a spin lock acquired by **KeAcquireSpinLockForDpc**. Pass the return value from **KeAcquireSpinLockForDpc** to **KeReleaseSpinLockForDpc**.

For more information about spin locks, see [Spin Locks](/windows-hardware/drivers/kernel/introduction-to-spin-locks).

## -see-also

[*CustomThreadedDpc*](/windows-hardware/drivers/kernel/introduction-to-threaded-dpcs)

[**KeInitializeSpinLock**](nf-wdm-keinitializespinlock.md)

[**KeReleaseSpinLockForDpc**](nf-wdm-kereleasespinlockfordpc.md)
