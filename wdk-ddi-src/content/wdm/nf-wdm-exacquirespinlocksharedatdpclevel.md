---
UID: NF:wdm.ExAcquireSpinLockSharedAtDpcLevel
tech.root: kernel
title: ExAcquireSpinLockSharedAtDpcLevel
ms.date: 10/03/2022
targetos: Windows
description: Learn more about the ExAcquireSpinLockSharedAtDpcLevel routine.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: IRQL >= DISPATCH_LEVEL
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
 - ExAcquireSpinLockSharedAtDpcLevel
f1_keywords:
 - ExAcquireSpinLockSharedAtDpcLevel
 - wdm/ExAcquireSpinLockSharedAtDpcLevel
dev_langs:
 - c++
helpviewer_keywords:
 - ExAcquireSpinLockSharedAtDpcLevel
---

## -description

The **ExAcquireSpinLockSharedAtDpcLevel** routine acquires a [spin lock](/windows-hardware/drivers/kernel/introduction-to-spin-locks) for shared access by a caller that is already running at IRQL \>= DISPATCH\_LEVEL.

## -parameters

### -param SpinLock

[in, out] A pointer to the spin lock to acquire for shared access. The caller must not already own this spin lock.

## -remarks

On entry to this routine, the caller must be running at IRQL \>= DISPATCH\_LEVEL. This routine does not change the IRQL.

To release the spin lock, the driver calls the [**ExReleaseSpinLockSharedFromDpcLevel**](nf-wdm-exreleasespinlocksharedfromdpclevel.md) routine.

A spin lock is a 32-bit variable of type EX\_SPIN\_LOCK. The driver must allocate the storage for the spin lock and initialize the spin lock to zero. This storage must be located in nonpaged system-space memory.

The caller should hold the spin lock only briefly before releasing it. For more information, see [Introduction to Spin Locks](/windows-hardware/drivers/kernel/introduction-to-spin-locks).

> [!NOTE]
> Recursive acquisition of a spin lock causes deadlock and is not allowed.

## -see-also

[**ExReleaseSpinLockSharedFromDpcLevel**](nf-wdm-exreleasespinlocksharedfromdpclevel.md)
