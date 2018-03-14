---
UID: NF:wdm.KeReleaseSpinLock
title: KeReleaseSpinLock macro
author: windows-driver-content
description: The KeReleaseSpinLock routine releases a spin lock and restores the original IRQL at which the caller was running.
old-location: kernel\kereleasespinlock.htm
old-project: kernel
ms.assetid: 300cdd3b-0c12-45e3-ae45-c26084f3ec12
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeReleaseSpinLock, KeReleaseSpinLock routine [Kernel-Mode Driver Architecture], k105_68224d09-0ef9-4231-af5f-c6f8761889dd.xml, kernel.kereleasespinlock, wdm/KeReleaseSpinLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeReleaseSpinLock, MarkingQueuedIrps, SpinLock, SpinLockDpc, SpinlockRelease, SpinLockSafe, ReqSendWhileSpinlock, Spinlock(kmdf), SpinlockDpc(kmdf), SpinlockRelease(kmdf), HwStorPortProhibitedDDIs, IrqlKeReleaseSpinLock(storport), SpinLock(storport), SpinLockDpc(storport), SpinLockRelease(storport), SpinLockSafe(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: DISPATCH_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hal.lib
-	Hal.dll
api_name:
-	KeReleaseSpinLock
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeReleaseSpinLock macro


## -description


The <b>KeReleaseSpinLock</b> routine releases a spin lock and restores the original IRQL at which the caller was running.


## -syntax


````
VOID KeReleaseSpinLock(
  _Inout_ PKSPIN_LOCK SpinLock,
  _In_    KIRQL       NewIrql
);
````


## -parameters




### -param a

TBD


### -param b

TBD






#### - NewIrql [in]

Specifies the IRQL value saved from the preceding call to <a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a>.


#### - SpinLock [in, out]

Pointer to a spin lock for which the caller provides the storage.


## -remarks



This call is a reciprocal to <a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a>. The input <i>NewIrql</i> value must be the <i>OldIrql</i> returned by <b>KeAcquireSpinLock</b>.

For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.

Callers of this routine are running at IRQL = DISPATCH_LEVEL. On return from <b>KeReleaseSpinLock</b>, IRQL is restored to the <i>NewIrql</i> value.




## -see-also

<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>



<a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a>



 

 


