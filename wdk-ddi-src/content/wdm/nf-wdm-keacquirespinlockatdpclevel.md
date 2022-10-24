---
UID: NF:wdm.KeAcquireSpinLockAtDpcLevel~r1
title: KeAcquireSpinLockAtDpcLevel macro (wdm.h)
description: The KeAcquireSpinLockAtDpcLevel routine acquires a spin lock when the caller is already running at IRQL >= DISPATCH_LEVEL.
tech.root: kernel
ms.date: 10/24/2022
keywords: ["KeAcquireSpinLockAtDpcLevel macro"]
ms.keywords: KeAcquireSpinLockAtDpcLevel, KeAcquireSpinLockAtDpcLevel routine [Kernel-Mode Driver Architecture], KefAcquireSpinLockAtDpcLevel, k105_4b7eb718-f04d-42de-9dfc-92355cd2ebc9.xml, kernel.keacquirespinlockatdpclevel, wdm/KeAcquireSpinLockAtDpcLevel, wdm/KefAcquireSpinLockAtDpcLevel
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
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - KeAcquireSpinLockAtDpcLevel
 - wdm/KeAcquireSpinLockAtDpcLevel
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeAcquireSpinLockAtDpcLevel
---

## -description

The **KeAcquireSpinLockAtDpcLevel** routine acquires a spin lock when the caller is already running at IRQL >= DISPATCH_LEVEL.

## -parameters

### -param SpinLock [in, out]

Pointer to an initialized KSPIN_LOCK spin lock for which the caller must provide the storage.  The spin lock must be from non-paged pool.

## -remarks

Drivers call **KeAcquireSpinLockAtDpcLevel** instead of [KeAcquireSpinLock](nf-wdm-keacquirespinlock.md) for better driver performance if and only if they are already running at an IRQL of DISPATCH_LEVEL or above.

If a driver is running at IRQL <= APC_LEVEL, it should call **KeAcquireSpinLock** to have IRQL raised by that routine. **KeAcquireSpinLockAtDpcLevel** assumes the caller is already running at IRQL >= DISPATCH_LEVEL, so no raise is necessary.

The caller should release the spin lock with [KeReleaseSpinLockFromDpcLevel](nf-wdm-kereleasespinlockfromdpclevel.md) as quickly as possible.

For more information about spin locks, see [Spin Locks](/windows-hardware/drivers/kernel/introduction-to-spin-locks.md).

## -see-also

[KeAcquireInStackQueuedSpinLockAtDpcLevel](nf-wdm-keacquireinstackqueuedspinlockatdpclevel.md)

[KeAcquireSpinLock](nf-wdm-keacquirespinlock.md)

[KeInitializeSpinLock](nf-wdm-keinitializespinlock.md)

[KeReleaseSpinLock](nf-wdm-kereleasespinlock.md)

[KeReleaseSpinLockFromDpcLevel](nf-wdm-kereleasespinlockfromdpclevel.md)

[KeTryToAcquireSpinLockAtDpcLevel](nf-wdm-ketrytoacquirespinlockatdpclevel.md)
