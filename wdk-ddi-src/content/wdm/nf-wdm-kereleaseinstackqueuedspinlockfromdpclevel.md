---
UID: NF:wdm.KeReleaseInStackQueuedSpinLockFromDpcLevel
title: KeReleaseInStackQueuedSpinLockFromDpcLevel function (wdm.h)
description: The KeReleaseInStackQueuedSpinLockFromDpcLevel routine releases a queued spin lock acquired by KeAcquireInStackQueuedSpinLockAtDpcLevel.
old-location: kernel\kereleaseinstackqueuedspinlockfromdpclevel.htm
tech.root: kernel
ms.assetid: c3f07b86-f5ca-4c21-bc4b-b23598da7664
ms.date: 04/30/2018
ms.keywords: KeReleaseInStackQueuedSpinLockFromDpcLevel, KeReleaseInStackQueuedSpinLockFromDpcLevel routine [Kernel-Mode Driver Architecture], k105_76a65a2a-d5b2-4066-90e9-4539c5e39930.xml, kernel.kereleaseinstackqueuedspinlockfromdpclevel, wdm/KeReleaseInStackQueuedSpinLockFromDpcLevel
ms.topic: function
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeReleaseInStackQueuedSpinLockFromDpcLevel function


## -description


The <b>KeReleaseInStackQueuedSpinLockFromDpcLevel</b> routine releases a queued spin lock acquired by <a href="https://msdn.microsoft.com/library/windows/hardware/ff551908">KeAcquireInStackQueuedSpinLockAtDpcLevel</a>.


## -parameters




### -param LockHandle [in]

Specifies the queued spin lock handle initialized by the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551908">KeAcquireInStackQueuedSpinLockAtDpcLevel</a> that acquired the lock.


## -returns



None




## -remarks



For more information about queued spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559970">Queued Spin Locks</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554247">KLOCK_QUEUE_HANDLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551908">KeAcquireInStackQueuedSpinLockAtDpcLevel</a>
 

 

