---
UID: NF:wdm.ExAcquireSpinLockExclusive
tech.root: kernel
title: ExAcquireSpinLockExclusive
ms.date: 10/03/2022
targetos: Windows
description: Learn more about the ExAcquireSpinLockExclusive routine.
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
req.target-min-winverclnt: Windows Vista SP1
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - wdm.h
api_name:
 - ExAcquireSpinLockExclusive
f1_keywords:
 - ExAcquireSpinLockExclusive
 - wdm/ExAcquireSpinLockExclusive
dev_langs:
 - c++
helpviewer_keywords:
 - ExAcquireSpinLockExclusive
---

## -description

The **ExAcquireSpinLockExclusive** routine acquires a [spin lock](/windows-hardware/drivers/kernel/introduction-to-spin-locks) for exclusive access by the caller, and raises the IRQL to DISPATCH\_LEVEL.

## -parameters

### -param SpinLock

[in, out] A pointer to the spin lock to acquire for exclusive access. The caller must not already own this spin lock.

## -returns

**ExAcquireSpinLockExclusive** returns the previous IRQL value. For more information, see Remarks.

## -remarks

On entry to this routine, the caller must be running at IRQL \<= DISPATCH\_LEVEL. This routine raises the IRQL to DISPATCH\_LEVEL and returns the original (on-entry) IRQL value.

To release the spin lock, call the [**ExReleaseSpinLockExclusive**](nf-wdm-exreleasespinlockexclusive.md) routine. **ExReleaseSpinLockExclusive** restores the IRQL to the original value that it had on entry to **ExAcquireSpinLockExclusive**.

A spin lock is a 32-bit variable of type EX\_SPIN\_LOCK. The driver must allocate the storage for the spin lock and initialize the spin lock to zero. This storage must be located in nonpaged system-space memory.

The caller should hold the spin lock only briefly before releasing it. For more information, see [Introduction to Spin Locks](/windows-hardware/drivers/kernel/introduction-to-spin-locks).

> [!NOTE]
> Recursive acquisition of a spin lock causes deadlock and is not allowed.

## -see-also

[**ExReleaseSpinLockExclusive**](nf-wdm-exreleasespinlockexclusive.md)
