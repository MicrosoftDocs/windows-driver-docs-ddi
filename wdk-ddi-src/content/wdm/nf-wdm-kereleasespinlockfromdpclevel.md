---
UID: NF:wdm.KeReleaseSpinLockFromDpcLevel~r1
title: KeReleaseSpinLockFromDpcLevel macro (wdm.h)
description: Learn how the KeReleaseSpinLockFromDpcLevel routine releases an executive spin lock without changing the IRQL.
tech.root: kernel
ms.date: 04/09/2025
keywords: ["KeReleaseSpinLockFromDpcLevel macro"]
ms.keywords: KeReleaseSpinLockFromDpcLevel, KeReleaseSpinLockFromDpcLevel routine [Kernel-Mode Driver Architecture], KefReleaseSpinLockFromDpcLevel, k105_ed15a49d-6903-4f9f-914c-668242701b1e.xml, kernel.kereleasespinlockfromdpclevel, wdm/KeReleaseSpinLockFromDpcLevel, wdm/KefReleaseSpinLockFromDpcLevel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs, IrqlDispatch, SpinLockSafe
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeReleaseSpinLockFromDpcLevel
 - wdm/KeReleaseSpinLockFromDpcLevel
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeReleaseSpinLockFromDpcLevel
---

## -description

The **KeReleaseSpinLockFromDpcLevel** routine releases an executive spin lock without changing the IRQL.

## -parameters

### -param SpinLock [in, out]

Pointer to an executive KSPIN_LOCK spin lock for which the caller provides the storage.

## -remarks

Drivers call **KeReleaseSpinLockFromDpcLevel** to release a spin lock acquired by calling [KeAcquireSpinLockAtDpcLevel](nf-wdm-keacquirespinlockatdpclevel.md).

It is an error to call **KeReleaseSpinLockFromDpcLevel** if the specified spin lock was acquired by calling [KeAcquireSpinLock](nf-wdm-keacquirespinlock.md) because the caller's original IRQL is not restored, which can cause deadlocks or fatal page faults.

For more information about spin locks, see [Spin Locks](/windows-hardware/drivers/kernel/spin-locks).

## -see-also

[KeAcquireInStackQueuedSpinLockAtDpcLevel](nf-wdm-keacquireinstackqueuedspinlockatdpclevel.md)

[KeAcquireSpinLock](nf-wdm-keacquirespinlock.md)

[KeAcquireSpinLockAtDpcLevel](nf-wdm-keacquirespinlockatdpclevel.md)

[KefReleaseSpinLockFromDpcLevel](nf-wdm-kefreleasespinlockfromdpclevel.md)

[KeInitializeSpinLock](nf-wdm-keinitializespinlock.md)

[KeReleaseSpinLock](nf-wdm-kereleasespinlock.md)

[KeTryToAcquireSpinLockAtDpcLevel](nf-wdm-ketrytoacquirespinlockatdpclevel.md)

[Spin Locks](/windows-hardware/drivers/kernel/spin-locks)
