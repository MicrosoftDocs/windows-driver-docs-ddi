---
UID: NF:wdm.KeInitializeSpinLock
title: KeInitializeSpinLock function (wdm.h)
description: The KeInitializeSpinLock routine initializes a variable of type KSPIN_LOCK.
tech.root: kernel
ms.date: 10/18/2022
keywords: ["KeInitializeSpinLock function"]
ms.keywords: KeInitializeSpinLock, KeInitializeSpinLock routine [Kernel-Mode Driver Architecture], k105_715eff59-827a-4d41-8e3a-2ce0d1f1181d.xml, kernel.keinitializespinlock, wdm/KeInitializeSpinLock
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
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - KeInitializeSpinLock
 - wdm/KeInitializeSpinLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeInitializeSpinLock
---

## -description

The **KeInitializeSpinLock** routine initializes a variable of type KSPIN_LOCK.

## -parameters

### -param SpinLock [out]

Pointer to a spin lock, for which the caller must provide the storage.

## -remarks

This routine must be called before an initial call to [KeAcquireSpinLock](nf-wdm-keacquirespinlock.md), to [KeAcquireInStackQueuedSpinLock](nf-wdm-keacquireinstackqueuedspinlock.md), or to any other support routine that requires a spin lock as an argument.

Storage for a spin lock object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

> [!NOTE]
> This function is inlined for x64 systems from Windows XP till Windows 7.
> Starting in Windows 8, this function is exported from `ntoskrnl.lib`. As a result, if you are using the Windows 10 WDK to build a binary that runs on Windows 7 (and therefore you need NX pool usage to pass Windows 10 HLK tests), you must define `WIN9X_COMPAT_SPINLOCK`.  Otherwise, you may see `Windows cannot load the device driver for this hardware. The driver may be corrupted or missing. (Code 39)`.

For more information about spin locks, see [Spin Locks](/windows-hardware/drivers/kernel/spin-locks).

Callers of this routine can be running at any IRQL. Usually, a caller is running at IRQL = PASSIVE_LEVEL in an [AddDevice](nc-wdm-driver_add_device.md) routine.

## -see-also

[KeAcquireInStackQueuedSpinLock](nf-wdm-keacquireinstackqueuedspinlock.md)

[KeAcquireInStackQueuedSpinLockAtDpcLevel](nf-wdm-keacquireinstackqueuedspinlockatdpclevel.md)

[KeAcquireSpinLock](nf-wdm-keacquirespinlock.md)

[KeAcquireSpinLockAtDpcLevel](nf-wdm-keacquirespinlockatdpclevel.md)

[KeReleaseInStackQueuedSpinLock](nf-wdm-kereleaseinstackqueuedspinlock.md)

[KeReleaseInStackQueuedSpinLockFromDpcLevel](nf-wdm-kereleaseinstackqueuedspinlockfromdpclevel.md)

[KeReleaseSpinLock](nf-wdm-kereleasespinlock.md)

[KeReleaseSpinLockFromDpcLevel](nf-wdm-kereleasespinlockfromdpclevel.md)
