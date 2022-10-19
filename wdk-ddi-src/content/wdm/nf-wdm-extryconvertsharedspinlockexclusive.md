---
UID: NF:wdm.ExTryConvertSharedSpinLockExclusive
title: ExTryConvertSharedSpinLockExclusive function (wdm.h)
description: The ExTryConvertSharedSpinLockExclusive routine attempts to convert the access state of a spin lock from acquired for shared access to exclusive access.
tech.root: kernel
ms.date: 10/18/2022
keywords: ["ExTryConvertSharedSpinLockExclusive function"]
ms.keywords: ExTryConvertSharedSpinLockExclusive, ExTryConvertSharedSpinLockExclusive routine [Kernel-Mode Driver Architecture], kernel.extryconvertsharedspinlockexclusive_, wdm/ExTryConvertSharedSpinLockExclusive
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExTryConvertSharedSpinLockExclusive
 - wdm/ExTryConvertSharedSpinLockExclusive
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ntoskrnl.lib
 - ntoskrnl.dll
api_name:
 - ExTryConvertSharedSpinLockExclusive
---

## -description

The **ExTryConvertSharedSpinLockExclusive** routine attempts to convert the access state of a [spin lock](/windows-hardware/drivers/kernel/introduction-to-spin-locks) from *acquired for shared access* to *exclusive access*.

## -parameters

### -param SpinLock [in, out]

A pointer to the spin lock whose access state is to be converted to exclusive access.  The caller must already own this spin lock for shared access.

## -returns

**ExTryConvertSharedSpinLockExclusive** returns TRUE if the conversion succeeds; otherwise, it returns FALSE.

## -remarks

If the caller acquired the shared spin lock by calling the [ExAcquireSpinLockSharedAtDpcLevel](nf-wdm-exacquirespinlocksharedatdpclevel.md) routine, the caller should release the converted spin lock by calling the [ExReleaseSpinLockExclusiveFromDpcLevel](nf-wdm-exreleasespinlockexclusivefromdpclevel.md) routine. If the caller acquired the shared spin lock by calling the [ExAcquireSpinLockShared](nf-wdm-exacquirespinlockshared.md) routine, the caller should release the converted spin lock by calling the [ExReleaseSpinLockExclusive](nf-wdm-exreleasespinlockexclusive.md) routine, and the *OldIrql* value supplied as an input parameter to this routine should be the KIRQL value returned by **ExAcquireSpinLockShared**.

## -see-also

[ExAcquireSpinLockShared](nf-wdm-exacquirespinlockshared.md)

[ExAcquireSpinLockSharedAtDpcLevel](nf-wdm-exacquirespinlocksharedatdpclevel.md)

[ExReleaseSpinLockExclusive](nf-wdm-exreleasespinlockexclusive.md)

[ExReleaseSpinLockExclusiveFromDpcLevel](nf-wdm-exreleasespinlockexclusivefromdpclevel.md)
