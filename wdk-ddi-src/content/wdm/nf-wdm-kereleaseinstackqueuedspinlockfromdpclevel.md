---
UID: NF:wdm.KeReleaseInStackQueuedSpinLockFromDpcLevel
title: KeReleaseInStackQueuedSpinLockFromDpcLevel function (wdm.h)
description: The KeReleaseInStackQueuedSpinLockFromDpcLevel routine releases a queued spin lock acquired by KeAcquireInStackQueuedSpinLockAtDpcLevel.
tech.root: kernel
ms.date: 10/18/2022
keywords: ["KeReleaseInStackQueuedSpinLockFromDpcLevel function"]
ms.keywords: KeReleaseInStackQueuedSpinLockFromDpcLevel, KeReleaseInStackQueuedSpinLockFromDpcLevel routine [Kernel-Mode Driver Architecture], k105_76a65a2a-d5b2-4066-90e9-4539c5e39930.xml, kernel.kereleaseinstackqueuedspinlockfromdpclevel, wdm/KeReleaseInStackQueuedSpinLockFromDpcLevel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KeReleaseInStackQueuedSpinLockFromDpcLevel
 - wdm/KeReleaseInStackQueuedSpinLockFromDpcLevel
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeReleaseInStackQueuedSpinLockFromDpcLevel
---

## -description

The **KeReleaseInStackQueuedSpinLockFromDpcLevel** routine releases a queued spin lock acquired by [KeAcquireInStackQueuedSpinLockAtDpcLevel](nf-wdm-keacquireinstackqueuedspinlockatdpclevel.md).

## -parameters

### -param LockHandle [in]

Specifies the queued spin lock handle initialized by the call to [KeAcquireInStackQueuedSpinLockAtDpcLevel](nf-wdm-keacquireinstackqueuedspinlockatdpclevel.md) that acquired the lock.

## -remarks

For more information about queued spin locks, see [Queued Spin Locks](/windows-hardware/drivers/kernel/queued-spin-locks).

## -see-also

[KLOCK_QUEUE_HANDLE](/windows-hardware/drivers/kernel/eprocess)

[KeAcquireInStackQueuedSpinLockAtDpcLevel](nf-wdm-keacquireinstackqueuedspinlockatdpclevel.md)
