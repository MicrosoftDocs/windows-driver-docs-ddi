---
UID: NF:wdm.ExReleaseSpinLockExclusive
title: ExReleaseSpinLockExclusive function
author: windows-driver-content
description: The ExReleaseSpinLockExclusive routine releases a spin lock that the caller previously acquired for exclusive access, and restores the IRQL to its original value.
old-location: kernel\exreleasespinlockexclusive_.htm
old-project: kernel
ms.assetid: D10C65A6-96E7-4BE0-BDD5-EFD129DC424C
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ExReleaseSpinLockExclusive, ExReleaseSpinLockExclusive routine [Kernel-Mode Driver Architecture], kernel.exreleasespinlockexclusive_, wdm/ExReleaseSpinLockExclusive
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista with SP1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL (See Remarks.)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	ExReleaseSpinLockExclusive
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExReleaseSpinLockExclusive function


## -description


The <b>ExReleaseSpinLockExclusive</b> routine releases a <a href="https://msdn.microsoft.com/a37c0db4-ff9c-4958-a9f4-62b671458d03">spin lock</a> that the caller previously acquired for exclusive access, and restores the IRQL to its original value.


## -syntax


````
VOID ExReleaseSpinLockExclusive (
  _Inout_ PEX_SPIN_LOCK SpinLock,
  _In_    KIRQL         OldIrql
);
````


## -parameters




### -param param

TBD


### -param OldIrql [in]

The interrupt request level (IRQL) to restore. Set this parameter to the KIRQL value that was returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451007">ExAcquireSpinLockExclusive</a> call that acquired the spin lock.


#### - SpinLock [in, out]

 A pointer to the spin lock to release. The caller must own this spin lock for exclusive access.


## -returns



None.




## -remarks



This routine must be called only for a spin lock that is owned by the caller.

On entry to this routine, the caller must be running at IRQL = DISPATCH_LEVEL. Before exiting, <b>ExReleaseSpinLockExclusive</b> restores the IRQL to the value specified by the <i>OldIrql</i> parameter.

The caller should hold the spin lock only briefly before releasing it. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548114">Introduction to Spin Locks</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451007">ExAcquireSpinLockExclusive</a>



 

 


