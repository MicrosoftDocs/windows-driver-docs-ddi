---
UID: NF:wdm.KeReleaseSpinLock~r1
title: KeReleaseSpinLock macro (wdm.h)
description: The KeReleaseSpinLock routine releases a spin lock and restores the original IRQL at which the caller was running.
tech.root: kernel
ms.date: 04/10/2025
keywords: ["KeReleaseSpinLock macro"]
ms.keywords: KeReleaseSpinLock, KeReleaseSpinLock routine [Kernel-Mode Driver Architecture], k105_68224d09-0ef9-4231-af5f-c6f8761889dd.xml, kernel.kereleasespinlock, wdm/KeReleaseSpinLock
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
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

## -description

The **KeReleaseSpinLock** routine releases a spin lock and restores the original IRQL at which the caller was running.

## -parameters

### -param SpinLock

Pointer to a KSPIN_LOCK spin lock for which the caller provides the storage.

### -param NewIrql

Specifies the KIRQL value saved from the preceding call to [**KeAcquireSpinLock**](nf-wdm-keacquirespinlock.md).

## -remarks

This call is a reciprocal to **KeAcquireSpinLock**. The input *NewIrql* value must be the *OldIrql* returned by **KeAcquireSpinLock**.

For more information about spin locks, see [Spin Locks](/windows-hardware/drivers/kernel/spin-locks).

Callers of this routine are running at IRQL = DISPATCH_LEVEL. On return from **KeReleaseSpinLock**, IRQL is restored to the *NewIrql* value.

## -see-also

[**KeAcquireSpinLock**](nf-wdm-keacquirespinlock.md)

[**KeInitializeSpinLock**](nf-wdm-keinitializespinlock.md)

[Spin Locks](/windows-hardware/drivers/kernel/spin-locks)
