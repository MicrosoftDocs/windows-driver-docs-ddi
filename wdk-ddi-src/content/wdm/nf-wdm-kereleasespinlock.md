---
UID: NF:wdm.KeReleaseSpinLock~r1
title: KeReleaseSpinLock macro (wdm.h)
description: The KeReleaseSpinLock routine releases a spin lock and restores the original IRQL at which the caller was running.
old-location: kernel\kereleasespinlock.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KeReleaseSpinLock macro"]
ms.keywords: KeReleaseSpinLock, KeReleaseSpinLock routine [Kernel-Mode Driver Architecture], k105_68224d09-0ef9-4231-af5f-c6f8761889dd.xml, kernel.kereleasespinlock, wdm/KeReleaseSpinLock
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeReleaseSpinLock, MarkingQueuedIrps, SpinLock, SpinLockDpc, SpinlockRelease, SpinLockSafe, ReqSendWhileSpinlock, Spinlock(kmdf), SpinlockDpc(kmdf), SpinlockRelease(kmdf), HwStorPortProhibitedDDIs, IrqlKeReleaseSpinLock(storport), SpinLock(storport), SpinLockDpc(storport), SpinLockRelease(storport), SpinLockSafe(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - KeReleaseSpinLock
 - wdm/KeReleaseSpinLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Hal.lib
 - Hal.dll
api_name:
 - KeReleaseSpinLock
---

# KeReleaseSpinLock macro


## -description

The <b>KeReleaseSpinLock</b> routine releases a spin lock and restores the original IRQL at which the caller was running.

## -parameters

### -param SpinLock [in]


Pointer to a KSPIN_LOCK spin lock for which the caller provides the storage.

### -param NewIrql [in, out]


Specifies the KIRQL value saved from the preceding call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a>.

## -syntax

```cpp
VOID
KeReleaseSpinLock (
    _Inout_ PKSPIN_LOCK SpinLock,
    _In_ _IRQL_restores_ KIRQL NewIrql
    );
```

## -remarks

This call is a reciprocal to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a>. The input <i>NewIrql</i> value must be the <i>OldIrql</i> returned by <b>KeAcquireSpinLock</b>.

For more information about spin locks, see <a href="/windows-hardware/drivers/kernel/spin-locks">Spin Locks</a>.

Callers of this routine are running at IRQL = DISPATCH_LEVEL. On return from <b>KeReleaseSpinLock</b>, IRQL is restored to the <i>NewIrql</i> value.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>
