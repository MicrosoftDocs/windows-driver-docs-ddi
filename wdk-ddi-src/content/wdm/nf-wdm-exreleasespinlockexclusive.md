---
UID: NF:wdm.ExReleaseSpinLockExclusive
title: ExReleaseSpinLockExclusive function (wdm.h)
description: The ExReleaseSpinLockExclusive routine releases a spin lock that the caller previously acquired for exclusive access, and restores the IRQL to its original value.
old-location: kernel\exreleasespinlockexclusive_.htm
tech.root: kernel
ms.date: 03/28/2018
keywords: ["ExReleaseSpinLockExclusive function"]
ms.keywords: ExReleaseSpinLockExclusive, ExReleaseSpinLockExclusive routine [Kernel-Mode Driver Architecture], kernel.exreleasespinlockexclusive_, wdm/ExReleaseSpinLockExclusive
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista with SP1.
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
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL (See Remarks.)
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
f1_keywords:
 - ExReleaseSpinLockExclusive
 - wdm/ExReleaseSpinLockExclusive
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - ExReleaseSpinLockExclusive
---

# ExReleaseSpinLockExclusive function


## -description

The <b>ExReleaseSpinLockExclusive</b> routine releases a <a href="/windows-hardware/drivers/kernel/introduction-to-spin-locks">spin lock</a> that the caller previously acquired for exclusive access, and restores the IRQL to its original value.

## -parameters

### -param param 

[in, out]
 A pointer to the spin lock to release. The caller must own this spin lock for exclusive access.

### -param OldIrql 

[in]
The interrupt request level (IRQL) to restore. Set this parameter to the KIRQL value that was returned by the <a href="/previous-versions/windows/hardware/drivers/hh451007(v=vs.85)">ExAcquireSpinLockExclusive</a> call that acquired the spin lock.

## -remarks

This routine must be called only for a spin lock that is owned by the caller.

On entry to this routine, the caller must be running at IRQL = DISPATCH_LEVEL. Before exiting, <b>ExReleaseSpinLockExclusive</b> restores the IRQL to the value specified by the <i>OldIrql</i> parameter.

The caller should hold the spin lock only briefly before releasing it. For more information, see <a href="/windows-hardware/drivers/kernel/introduction-to-spin-locks">Introduction to Spin Locks</a>.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/hh451007(v=vs.85)">ExAcquireSpinLockExclusive</a>
