---
UID: NF:wdm.KeAcquireSpinLockAtDpcLevel
title: KeAcquireSpinLockAtDpcLevel macro
author: windows-driver-content
description: The KeAcquireSpinLockAtDpcLevel routine acquires a spin lock when the caller is already running at IRQL &gt;= DISPATCH_LEVEL.
old-location: kernel\keacquirespinlockatdpclevel.htm
tech.root: kernel
ms.assetid: 010b5e42-26c7-433f-b67b-1afdc0ec564c
ms.date: 4/30/2018
ms.keywords: KeAcquireSpinLockAtDpcLevel, KeAcquireSpinLockAtDpcLevel routine [Kernel-Mode Driver Architecture], KefAcquireSpinLockAtDpcLevel, k105_4b7eb718-f04d-42de-9dfc-92355cd2ebc9.xml, kernel.keacquirespinlockatdpclevel, wdm/KeAcquireSpinLockAtDpcLevel, wdm/KefAcquireSpinLockAtDpcLevel
ms.topic: macro
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeAcquireSpinLockAtDpcLevel
-	KefAcquireSpinLockAtDpcLevel
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeAcquireSpinLockAtDpcLevel macro


## -description


The <b>KeAcquireSpinLockAtDpcLevel</b> routine acquires a spin lock when the caller is already running at IRQL &gt;= DISPATCH_LEVEL. 


## -parameters




### -param a [in, out]

Pointer to an initialized spin lock for which the caller must provide the storage.





## -remarks



Drivers call <b>KeAcquireSpinLockAtDpcLevel</b> instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551917">KeAcquireSpinLock</a> for better driver performance if and only if they are already running at an IRQL of DISPATCH_LEVEL or above.

If a driver is running at IRQL &lt;= APC_LEVEL, it should call <b>KeAcquireSpinLock</b> to have IRQL raised by that routine. <b>KeAcquireSpinLockAtDpcLevel</b> assumes the caller is already running at IRQL &gt;= DISPATCH_LEVEL, so no raise is necessary.

The caller should release the spin lock with <a href="https://msdn.microsoft.com/library/windows/hardware/ff553150">KeReleaseSpinLockFromDpcLevel</a> as quickly as possible.

For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551908">KeAcquireInStackQueuedSpinLockAtDpcLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551917">KeAcquireSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553145">KeReleaseSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553150">KeReleaseSpinLockFromDpcLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553317">KeTryToAcquireSpinLockAtDpcLevel</a>
 

 

