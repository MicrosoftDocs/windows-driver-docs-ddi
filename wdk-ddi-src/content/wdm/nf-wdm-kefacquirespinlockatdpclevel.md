---
UID: NF:wdm.KefAcquireSpinLockAtDpcLevel
tech.root: kernel
title: KefAcquireSpinLockAtDpcLevel
ms.date: 05/20/2025
targetos: Windows
description: The KefAcquireSpinLockAtDpcLevel routine acquires a spin lock when the caller is already running at IRQL >= DISPATCH_LEVEL.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.kmdf-ver: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - KefAcquireSpinLockAtDpcLevel
f1_keywords:
 - KefAcquireSpinLockAtDpcLevel
 - wdm/KefAcquireSpinLockAtDpcLevel
dev_langs:
 - c++
helpviewer_keywords:
 - KefAcquireSpinLockAtDpcLevel
---

## -description

The **KefAcquireSpinLockAtDpcLevel** routine acquires a spin lock when the caller is already running at IRQL >= DISPATCH_LEVEL.

## -parameters

### -param SpinLock

Pointer to an initialized KSPIN_LOCK spin lock for which the caller must provide the storage. The spin lock must be from non-paged pool.

## -remarks

Drivers call **KefAcquireSpinLockAtDpcLevel** instead of **[KeAcquireSpinLock](nf-wdm-keacquirespinlock.md)** for better driver performance if and only if they are already running at an IRQL of DISPATCH_LEVEL or above.

If a driver is running at IRQL <= APC_LEVEL, it should call KeAcquireSpinLock to have IRQL raised by that routine. **KefAcquireSpinLockAtDpcLevel** assumes the caller is already running at IRQL >= DISPATCH_LEVEL, so no raise is necessary.

The caller should release the spin lock with **[KefReleaseSpinLockFromDpcLevel](nf-wdm-kefreleasespinlockfromdpclevel.md)** as quickly as possible.

For more information about spin locks, see [Spin Locks](/windows-hardware/drivers/kernel/introduction-to-spin-locks).

## -see-also

- **[KeAcquireInStackQueuedSpinLockAtDpcLevel](nf-wdm-keacquireinstackqueuedspinlockatdpclevel.md)**
- **[KeAcquireSpinLock](nf-wdm-keacquirespinlock.md)**
- **[KeAcquireSpinLockAtDpcLevel](nf-wdm-keacquirespinlockatdpclevel.md)**
- **[KefReleaseSpinLockFromDpcLevel](nf-wdm-kefreleasespinlockfromdpclevel.md)**
- **[KeInitializeSpinLock](nf-wdm-keinitializespinlock.md)**
- **[KeReleaseSpinLock](nf-wdm-kereleasespinlock.md)**
- **[KeReleaseSpinLockFromDpcLevel](nf-wdm-kereleasespinlockfromdpclevel.md)**
- **[KeTryToAcquireSpinLockAtDpcLevel](nf-wdm-ketrytoacquirespinlockatdpclevel.md)**
- [Spin Locks](/windows-hardware/drivers/kernel/spin-locks)
