---
UID: NF:wdm.KeAcquireSpinLockRaiseToDpc
tech.root: kernel
title: KeAcquireSpinLockRaiseToDpc
ms.date: 10/05/2022
targetos: Windows
description: The KeAcquireSpinLockRaiseToDpc routine is a faster version of the KeAcquireSpinLock routine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000 64-bit
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
 - KeAcquireSpinLockRaiseToDpc
f1_keywords:
 - KeAcquireSpinLockRaiseToDpc
 - wdm/KeAcquireSpinLockRaiseToDpc
dev_langs:
 - c++
helpviewer_keywords:
 - KeAcquireSpinLockRaiseToDpc
---

## -description

The **KeAcquireSpinLockRaiseToDpc** routine is a faster version of the [**KeAcquireSpinLock**](nf-wdm-keacquirespinlock.md) routine.

## -parameters

### -param SpinLock

[in, out] Specifies the spin lock to acquire. The spin lock must already have been initialized by [**KeInitializeSpinLock**](nf-wdm-keinitializespinlock.md).

## -returns

**KeAcquireSpinLockRaiseToDpc** returns the current IRQL at the time the routine is called. This value is passed to [**KeReleaseSpinLock**](nf-wdm-kereleasespinlock.md)) when the spin lock is released.

## -remarks

The effect of this routine is identical to that of [**KeAcquireSpinLock**](nf-wdm-keacquirespinlock.md). In particular, the acquired spin lock is released by [**KeReleaseSpinLock**](nf-wdm-kereleasespinlock.md). For more information, see the reference page for **KeAcquireSpinLock**.

Drivers can try to acquire the spin lock without blocking by using [**KeTryToAcquireSpinLockAtDpcLevel**](nf-wdm-ketrytoacquirespinlockatdpclevel.md).

For more information about spin locks, see [Spin Locks](/windows-hardware/drivers/kernel/introduction-to-spin-locks).

## -see-also

[**KeAcquireInStackQueuedSpinLock**](nf-wdm-keacquireinstackqueuedspinlock.md)

[**KeAcquireSpinLock**](nf-wdm-keacquirespinlock.md)

[**KeInitializeSpinLock**](nf-wdm-keinitializespinlock.md)
