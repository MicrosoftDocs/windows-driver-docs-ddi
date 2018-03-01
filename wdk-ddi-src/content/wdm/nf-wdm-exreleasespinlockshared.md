---
UID: NF:wdm.ExReleaseSpinLockShared
title: ExReleaseSpinLockShared function
author: windows-driver-content
description: The ExReleaseSpinLockShared routine releases ownership of a spin lock that the caller previously acquired for shared access, and restores the IRQL to its original value.
old-location: kernel\exreleasespinlockshared_.htm
old-project: kernel
ms.assetid: D79FD160-1A03-43F0-B9AB-D74C6176565A
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ExReleaseSpinLockShared, ExReleaseSpinLockShared routine [Kernel-Mode Driver Architecture], kernel.exreleasespinlockshared_, wdm/ExReleaseSpinLockShared
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
req.lib: NtosKrnl.exe
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
-	ExReleaseSpinLockShared
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExReleaseSpinLockShared function


## -description


The <b>ExReleaseSpinLockShared</b> routine releases ownership of a  <a href="https://msdn.microsoft.com/a37c0db4-ff9c-4958-a9f4-62b671458d03">spin lock</a> that the caller previously acquired for shared access, and restores the IRQL to its original value.


## -syntax


````
VOID ExReleaseSpinLockShared (
  _Inout_ PEX_SPIN_LOCK SpinLock,
  _In_    KIRQL         OldIrql
);
````


## -parameters




### -param param

TBD


### -param OldIrql [in]

The interrupt request level (IRQL) to restore. Set this parameter to the KIRQL value that was returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451053">ExAcquireSpinLockShared</a> call that acquired the spin lock.


#### - SpinLock [in, out]

A pointer to the spin lock to release. The caller must own this spin lock for shared access.


## -returns



None.




## -remarks



This routine must be called only for a spin lock that is owned by the caller.

On entry to this routine, the caller must be running at IRQL = DISPATCH_LEVEL. Before exiting, <b>ExReleaseSpinLockShared</b> restores the IRQL to the value specified by the <i>OldIrql</i> parameter.

The caller should hold the spin lock only briefly before releasing it. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548114">Introduction to Spin Locks</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451053">ExAcquireSpinLockShared</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExReleaseSpinLockShared  routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

