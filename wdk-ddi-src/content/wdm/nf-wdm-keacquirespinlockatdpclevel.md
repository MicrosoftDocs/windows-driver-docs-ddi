---
UID: NF:wdm.KeAcquireSpinLockAtDpcLevel~r1
title: KeAcquireSpinLockAtDpcLevel macro (wdm.h)
description: The KeAcquireSpinLockAtDpcLevel routine acquires a spin lock when the caller is already running at IRQL >= DISPATCH_LEVEL.
old-location: kernel\keacquirespinlockatdpclevel.htm
tech.root: kernel
ms.assetid: 010b5e42-26c7-433f-b67b-1afdc0ec564c
ms.date: 04/30/2018
keywords: ["KeAcquireSpinLockAtDpcLevel macro"]
ms.keywords: KeAcquireSpinLockAtDpcLevel, KeAcquireSpinLockAtDpcLevel routine [Kernel-Mode Driver Architecture], KefAcquireSpinLockAtDpcLevel, k105_4b7eb718-f04d-42de-9dfc-92355cd2ebc9.xml, kernel.keacquirespinlockatdpclevel, wdm/KeAcquireSpinLockAtDpcLevel, wdm/KefAcquireSpinLockAtDpcLevel
f1_keywords:
 - "wdm/KeAcquireSpinLockAtDpcLevel"
 - "KeAcquireSpinLockAtDpcLevel"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeAcquireSpinLockAtDpcLevel
- KefAcquireSpinLockAtDpcLevel
targetos: Windows
req.typenames: 
---

# KeAcquireSpinLockAtDpcLevel macro


## -description


The <b>KeAcquireSpinLockAtDpcLevel</b> routine acquires a spin lock when the caller is already running at IRQL >= DISPATCH_LEVEL. 


## -parameters




### -param SpinLock 
[in, out]
Pointer to an initialized KSPIN_LOCK spin lock for which the caller must provide the storage.  The spin lock must be from non-paged pool.





## -remarks



Drivers call <b>KeAcquireSpinLockAtDpcLevel</b> instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a> for better driver performance if and only if they are already running at an IRQL of DISPATCH_LEVEL or above.

If a driver is running at IRQL <= APC_LEVEL, it should call <b>KeAcquireSpinLock</b> to have IRQL raised by that routine. <b>KeAcquireSpinLockAtDpcLevel</b> assumes the caller is already running at IRQL >= DISPATCH_LEVEL, so no raise is necessary.

The caller should release the spin lock with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereleasespinlockfromdpclevel">KeReleaseSpinLockFromDpcLevel</a> as quickly as possible.

For more information about spin locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/spin-locks">Spin Locks</a>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551908(v=vs.85)">KeAcquireInStackQueuedSpinLockAtDpcLevel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereleasespinlock">KeReleaseSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereleasespinlockfromdpclevel">KeReleaseSpinLockFromDpcLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553317">KeTryToAcquireSpinLockAtDpcLevel</a>
 

 

