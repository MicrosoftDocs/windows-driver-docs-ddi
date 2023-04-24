---
UID: NF:wdm.ExAcquireSpinLockShared
title: ExAcquireSpinLockShared
description: The ExAcquireSpinLockShared routine acquires a spin lock for shared access by the caller, and raises the IRQL to DISPATCH_LEVEL.
tech.root:  kernel
ms.date: 01/05/2023
targetos: Windows
prerelease: false
keywords: ["ExAcquireSpinLockShared function"]
ms.keywords: ExAcquireSpinLockShared, ExAcquireSpinLockShared routine [Kernel-Mode Driver Architecture], kernel.exacquirespinlockshared_, wdm/ExAcquireSpinLockShared
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: DISPATCH_LEVEL (See Remarks.)
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.product: Windows 10 or later.
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.typenames: WORK_QUEUE_TYPE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - ExAcquireSpinLockShared
f1_keywords:
 - ExAcquireSpinLockShared
 - wdm/ExAcquireSpinLockShared
dev_langs:
 - c++
helpviewer_keywords:
 - ExAcquireSpinLockShared
---

## -description

The **ExAcquireSpinLockShared** routine acquires a [spin lock](/windows-hardware/drivers/kernel/introduction-to-spin-locks) for shared access by the caller, and raises the IRQL to DISPATCH_LEVEL.

## -parameters

### -param SpinLock [in, out]

A pointer to the spin lock to acquire for shared access. The caller must not already own this spin lock.

## -returns

The ExAcquireSpinLockShared routine returns the previous IRQL value. For more information, see the [Remarks](#remarks) section.

## -remarks

On entry to this routine, the caller must be running at IRQL <= DISPATCH_LEVEL. This routine raises the IRQL to DISPATCH_LEVEL and returns the original (on-entry) IRQL value.

To release the spin lock, call the [**ExReleaseSpinLockShared**](nf-wdm-exreleasespinlockshared.md) routine. **ExReleaseSpinLockShared** restores the IRQL to the original value that it had on entry to **ExAcquireSpinLockShared**.

A spin lock is a 32-bit variable of type EX_SPIN_LOCK. The driver must allocate the storage for the spin lock and initialize the spin lock to zero. This storage must be located in nonpaged system-space memory.

The caller should hold the spin lock only briefly before releasing it. For more information, see [Introduction to Spin Locks](/windows-hardware/drivers/kernel/introduction-to-spin-locks).

Recursive acquisition of a spin lock causes deadlock and is not allowed.

## -see-also

[**ExReleaseSpinLockShared**](nf-wdm-exreleasespinlockshared.md)
