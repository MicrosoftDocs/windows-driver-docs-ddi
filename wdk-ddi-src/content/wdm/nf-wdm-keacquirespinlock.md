---
UID: NF:wdm.KeAcquireSpinLock
title: KeAcquireSpinLock macro
description: The KeAcquireSpinLock routine acquires a spin lock so the caller can synchronize access to shared data in a multiprocessor-safe way by raising IRQL.
old-location: kernel\keacquirespinlock.htm
tech.root: kernel
ms.assetid: 10999175-4793-4045-8a74-a9a491724ec9
ms.date: 04/30/2018
ms.keywords: KeAcquireSpinLock, KeAcquireSpinLock routine [Kernel-Mode Driver Architecture], k105_387b61b6-b20f-4f17-be47-74c9ed3ac8a1.xml, kernel.keacquirespinlock, wdm/KeAcquireSpinLock
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeDispatchLte, MarkingQueuedIrps, SpinLock, SpinLockDpc, SpinlockRelease, SpinLockSafe, ReqSendWhileSpinlock, Spinlock(kmdf), SpinlockDpc(kmdf), SpinlockRelease(kmdf), HwStorPortProhibitedDDIs, SpinLock(storport), SpinLockDpc(storport), SpinLockRelease(storport), SpinLockSafe(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hal.lib
-	Hal.dll
api_name:
-	KeAcquireSpinLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeAcquireSpinLock macro


## -description


The <b>KeAcquireSpinLock</b> routine acquires a spin lock so the caller can synchronize access to shared data in a multiprocessor-safe way by raising IRQL.


## -parameters




### -param a
Pointer to an initialized KSPIN_LOCK spin lock for which the caller provides the storage.



### -param b
Pointer to a KIRQL variable that is set to the current IRQL when this call occurs.



## -remarks



<b>KeAcquireSpinLock</b> first resets the IRQL to DISPATCH_LEVEL and then acquires the lock. The previous IRQL is written to <i>OldIrql</i> after the lock is acquired.

The <i>OldIrql</i> value must be specified when the spin lock is released with <a href="https://msdn.microsoft.com/library/windows/hardware/ff553145">KeReleaseSpinLock</a>.

Most drivers use a local variable to store the old IRQL value. A driver can also use a shared memory location, such as a global variable, but the driver must not use the same location for two different locks. Otherwise, a race condition can occur.

Spin locks can cause serious problems if not used judiciously. In particular, no deadlock protection is performed and dispatching is disabled while the spin lock is held. Therefore:

<ul>
<li>
The code within a critical region guarded by an spin lock must neither be pageable nor make any references to pageable data.

</li>
<li>
The code within a critical region guarded by a spin lock can neither call any external function that might access pageable data or raise an exception, nor can it generate any exceptions.

</li>
<li>
The caller should release the spin lock with <b>KeReleaseSpinLock</b> as quickly as possible.

</li>
</ul>
Attempting to acquire a spin lock recursively is guaranteed to cause a deadlock. For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551899">KeAcquireInStackQueuedSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551921">KeAcquireSpinLockAtDpcLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553145">KeReleaseSpinLock</a>
 

 

