---
UID: NF:wdm.ExReleaseSpinLockSharedFromDpcLevel
tech.root: kernel
title: ExReleaseSpinLockSharedFromDpcLevel
ms.date: 10/05/2022
targetos: Windows
description: Learn more about the ExReleaseSpinLockSharedFromDpcLevel routine.
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
 - ExReleaseSpinLockSharedFromDpcLevel
f1_keywords:
 - ExReleaseSpinLockSharedFromDpcLevel
 - wdm/ExReleaseSpinLockSharedFromDpcLevel
dev_langs:
 - c++
helpviewer_keywords:
 - ExReleaseSpinLockSharedFromDpcLevel
---

## -description

The **ExReleaseSpinLockSharedFromDpcLevel** routine releases a [spin lock](/windows-hardware/drivers/kernel/introduction-to-spin-locks) that the caller acquired for shared access, and leaves the IRQL unchanged.

## -parameters

### -param SpinLock

[in, out] A pointer to the spin lock to release. The caller must own this spin lock for shared access.

## -remarks

On entry to this routine, the caller must be running at IRQL \>= DISPATCH\_LEVEL. This routine does not change the IRQL.

**ExReleaseSpinLockSharedFromDpcLevel** releases a spin lock that the caller acquired in a previous call to the [**ExAcquireSpinLockSharedAtDpcLevel**](nf-wdm-exacquirespinlocksharedatdpclevel.md) routine.

The caller should hold the spin lock only briefly before releasing it. For more information, see [Introduction to Spin Locks](/windows-hardware/drivers/kernel/introduction-to-spin-locks).

## -see-also

[**ExAcquireSpinLockSharedAtDpcLevel**](hh45nf-wdm-exacquirespinlocksharedatdpclevel.md)
