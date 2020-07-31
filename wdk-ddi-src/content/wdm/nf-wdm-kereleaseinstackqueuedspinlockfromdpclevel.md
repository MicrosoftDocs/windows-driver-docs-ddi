---
UID: NF:wdm.KeReleaseInStackQueuedSpinLockFromDpcLevel
title: KeReleaseInStackQueuedSpinLockFromDpcLevel function (wdm.h)
description: The KeReleaseInStackQueuedSpinLockFromDpcLevel routine releases a queued spin lock acquired by KeAcquireInStackQueuedSpinLockAtDpcLevel.
old-location: kernel\kereleaseinstackqueuedspinlockfromdpclevel.htm
tech.root: kernel
ms.assetid: c3f07b86-f5ca-4c21-bc4b-b23598da7664
ms.date: 04/30/2018
keywords: ["KeReleaseInStackQueuedSpinLockFromDpcLevel function"]
ms.keywords: KeReleaseInStackQueuedSpinLockFromDpcLevel, KeReleaseInStackQueuedSpinLockFromDpcLevel routine [Kernel-Mode Driver Architecture], k105_76a65a2a-d5b2-4066-90e9-4539c5e39930.xml, kernel.kereleaseinstackqueuedspinlockfromdpclevel, wdm/KeReleaseInStackQueuedSpinLockFromDpcLevel
f1_keywords:
 - "wdm/KeReleaseInStackQueuedSpinLockFromDpcLevel"
 - "KeReleaseInStackQueuedSpinLockFromDpcLevel"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeReleaseInStackQueuedSpinLockFromDpcLevel
targetos: Windows
req.typenames: 
---

# KeReleaseInStackQueuedSpinLockFromDpcLevel function


## -description


The <b>KeReleaseInStackQueuedSpinLockFromDpcLevel</b> routine releases a queued spin lock acquired by <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551908(v=vs.85)">KeAcquireInStackQueuedSpinLockAtDpcLevel</a>.


## -parameters




### -param LockHandle [in]

Specifies the queued spin lock handle initialized by the call to <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551908(v=vs.85)">KeAcquireInStackQueuedSpinLockAtDpcLevel</a> that acquired the lock.


## -remarks



For more information about queued spin locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/queued-spin-locks">Queued Spin Locks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KLOCK_QUEUE_HANDLE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551908(v=vs.85)">KeAcquireInStackQueuedSpinLockAtDpcLevel</a>
 

 

