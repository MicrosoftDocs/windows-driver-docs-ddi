---
UID: NF:wdm.ExTryConvertSharedSpinLockExclusive
title: ExTryConvertSharedSpinLockExclusive function
author: windows-driver-content
description: The ExTryConvertSharedSpinLockExclusive routine attempts to convert the access state of a spin lock from acquired for shared access to exclusive access.
old-location: kernel\extryconvertsharedspinlockexclusive_.htm
old-project: kernel
ms.assetid: 6B97865A-D589-4116-8492-109BEEE93ECA
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ExTryConvertSharedSpinLockExclusive, ExTryConvertSharedSpinLockExclusive routine [Kernel-Mode Driver Architecture], kernel.extryconvertsharedspinlockexclusive_, wdm/ExTryConvertSharedSpinLockExclusive
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ntoskrnl.lib
-	ntoskrnl.dll
api_name:
-	ExTryConvertSharedSpinLockExclusive
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExTryConvertSharedSpinLockExclusive function


## -description


The <b>ExTryConvertSharedSpinLockExclusive</b> routine attempts to convert the access state of a <a href="https://msdn.microsoft.com/a37c0db4-ff9c-4958-a9f4-62b671458d03">spin lock</a> from <i>acquired for shared access</i> to <i>exclusive access</i>.


## -syntax


````
BOOLEAN ExTryConvertSharedSpinLockExclusive(
  _Inout_ PEX_SPIN_LOCK  SpinLock
);
````


## -parameters




### -param SpinLock [in, out]

A pointer to the spin lock whose access state is to be converted to exclusive access.  The caller must already own this spin lock for shared access.


## -returns



<b>ExTryConvertSharedSpinLockExclusive</b> returns TRUE if the conversion succeeds; otherwise, it returns FALSE.




## -remarks



If the caller acquired the shared spin lock by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451055">ExAcquireSpinLockSharedAtDpcLevel</a> routine, the caller should release the converted spin lock by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451058">ExReleaseSpinLockExclusiveFromDpcLevel</a> routine. If the caller acquired the shared spin lock by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451053">ExAcquireSpinLockShared</a> routine, the caller should release the converted spin lock by calling the <a href="..\wdm\nf-wdm-exreleasespinlockexclusive.md">ExReleaseSpinLockExclusive</a> routine, and the <i>OldIrql</i> value supplied as an input parameter to this routine should be the KIRQL value returned by <b>ExAcquireSpinLockShared</b>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451055">ExAcquireSpinLockSharedAtDpcLevel</a>



<a href="..\wdm\nf-wdm-exreleasespinlockexclusive.md">ExReleaseSpinLockExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451058">ExReleaseSpinLockExclusiveFromDpcLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451053">ExAcquireSpinLockShared</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExTryConvertSharedSpinLockExclusive routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

