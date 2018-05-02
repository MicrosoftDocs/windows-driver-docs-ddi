---
UID: NF:wdm.KeReleaseInStackQueuedSpinLockForDpc
title: KeReleaseInStackQueuedSpinLockForDpc function
author: windows-driver-content
description: The KeReleaseInStackQueuedSpinLockForDpc routine releases a queued spin lock that was acquired by calling KeAcquireInStackQueuedSpinLockForDpc.
old-location: kernel\kereleaseinstackqueuedspinlockfordpc.htm
old-project: kernel
ms.assetid: 4334559f-a07c-4d11-952b-97717232f74f
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeReleaseInStackQueuedSpinLockForDpc, KeReleaseInStackQueuedSpinLockForDpc routine [Kernel-Mode Driver Architecture], k105_19c82f3d-cecf-4c77-9800-4b80c63db572.xml, kernel.kereleaseinstackqueuedspinlockfordpc, wdm/KeReleaseInStackQueuedSpinLockForDpc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeReleaseInStackQueuedSpinLockForDpc
product: Windows
targetos: Windows
req.typenames: 
---

# KeReleaseInStackQueuedSpinLockForDpc function


## -description


The <b>KeReleaseInStackQueuedSpinLockForDpc</b> routine releases a queued spin lock that was acquired by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff551912">KeAcquireInStackQueuedSpinLockForDpc</a>.


## -parameters




### -param LockHandle [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554247">KLOCK_QUEUE_HANDLE</a> structure that <a href="https://msdn.microsoft.com/library/windows/hardware/ff551912">KeAcquireInStackQueuedSpinLockForDpc</a> initialized when the queued spin lock was acquired.


## -returns



None




## -remarks



For more information about queued spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559970">Queued Spin Locks</a>.

If the current IRQL was PASSIVE_LEVEL when the queued spin lock was acquired, <b>KeReleaseSpinLockForDpc</b> lowers the current IRQL to PASSIVE_LEVEL. If the current IRQL was DISPATCH_LEVEL when the queued spin lock was acquired, <b>KeReleaseSpinLockForDpc</b> does not change the current IRQL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554247">KLOCK_QUEUE_HANDLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551912">KeAcquireInStackQueuedSpinLockForDpc</a>
 

 

