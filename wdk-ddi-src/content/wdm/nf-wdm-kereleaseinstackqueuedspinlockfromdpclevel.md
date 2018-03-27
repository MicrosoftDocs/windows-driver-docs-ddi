---
UID: NF:wdm.KeReleaseInStackQueuedSpinLockFromDpcLevel
title: KeReleaseInStackQueuedSpinLockFromDpcLevel function
author: windows-driver-content
description: The KeReleaseInStackQueuedSpinLockFromDpcLevel routine releases a queued spin lock acquired by KeAcquireInStackQueuedSpinLockAtDpcLevel.
old-location: kernel\kereleaseinstackqueuedspinlockfromdpclevel.htm
old-project: kernel
ms.assetid: c3f07b86-f5ca-4c21-bc4b-b23598da7664
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeReleaseInStackQueuedSpinLockFromDpcLevel, KeReleaseInStackQueuedSpinLockFromDpcLevel routine [Kernel-Mode Driver Architecture], k105_76a65a2a-d5b2-4066-90e9-4539c5e39930.xml, kernel.kereleaseinstackqueuedspinlockfromdpclevel, wdm/KeReleaseInStackQueuedSpinLockFromDpcLevel
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeReleaseInStackQueuedSpinLockFromDpcLevel
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeReleaseInStackQueuedSpinLockFromDpcLevel routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

