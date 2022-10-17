---
UID: NF:wdm.ExAcquireSpinLockExclusiveAtDpcLevel
tech.root: kernel
title: ExAcquireSpinLockExclusiveAtDpcLevel
ms.date: 10/03/2022
targetos: Windows
description: Learn more about the ExAcquireSpinLockExclusiveAtDpcLevel routine.
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
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - ExAcquireSpinLockExclusiveAtDpcLevel
f1_keywords:
 - ExAcquireSpinLockExclusiveAtDpcLevel
 - wdm/ExAcquireSpinLockExclusiveAtDpcLevel
dev_langs:
 - c++
helpviewer_keywords:
 - ExAcquireSpinLockExclusiveAtDpcLevel
---

## -description

The **ExAcquireSpinLockExclusiveAtDpcLevel** routine acquires a [spin lock](/windows-hardware/drivers/kernel/introduction-to-spin-locks) for exclusive access by a caller that is already running at IRQL \>= DISPATCH\_LEVEL.

## -parameters

### -param SpinLock

[in, out] A pointer to the spin lock to acquire. The caller must not already own this spin lock.

## -remarks

On entry to this routine, the caller must be running at IRQL \>= DISPATCH\_LEVEL. This routine does not change the IRQL.

To release the spin lock, the driver calls the [**ExReleaseSpinLockExclusiveFromDpcLevel**](nf-wdm-exreleasespinlockexclusivefromdpclevel.md) routine.

A spin lock is a 32-bit variable of type EX\_SPIN\_LOCK. The driver must allocate the storage for the spin lock and initialize the spin lock to zero. This storage must be located in nonpaged system-space memory.

The caller should hold the spin lock only briefly before releasing it. For more information, see [Introduction to Spin Locks](/windows-hardware/drivers/kernel/introduction-to-spin-locks).

> [!NOTE]
> Recursive acquisition of a spin lock causes deadlock and is not allowed.

## -see-also

[**ExReleaseSpinLockExclusiveFromDpcLevel**](nf-wdm-exreleasespinlockexclusivefromdpclevel.md)
