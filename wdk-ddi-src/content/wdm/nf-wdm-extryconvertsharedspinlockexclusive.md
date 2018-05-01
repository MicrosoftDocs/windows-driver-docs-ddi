---
UID: NF:wdm.ExTryConvertSharedSpinLockExclusive
title: ExTryConvertSharedSpinLockExclusive function
author: windows-driver-content
description: The ExTryConvertSharedSpinLockExclusive routine attempts to convert the access state of a spin lock from acquired for shared access to exclusive access.
old-location: kernel\extryconvertsharedspinlockexclusive_.htm
old-project: kernel
ms.assetid: 6B97865A-D589-4116-8492-109BEEE93ECA
ms.author: windowsdriverdev
ms.date: 4/5/2018
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
req.typenames: 
---

# ExTryConvertSharedSpinLockExclusive function


## -description


The <b>ExTryConvertSharedSpinLockExclusive</b> routine attempts to convert the access state of a <a href="https://msdn.microsoft.com/a37c0db4-ff9c-4958-a9f4-62b671458d03">spin lock</a> from <i>acquired for shared access</i> to <i>exclusive access</i>.


## -parameters




### -param SpinLock [in, out]

A pointer to the spin lock whose access state is to be converted to exclusive access.  The caller must already own this spin lock for shared access.


## -returns



<b>ExTryConvertSharedSpinLockExclusive</b> returns TRUE if the conversion succeeds; otherwise, it returns FALSE.




## -remarks



If the caller acquired the shared spin lock by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451055">ExAcquireSpinLockSharedAtDpcLevel</a> routine, the caller should release the converted spin lock by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451058">ExReleaseSpinLockExclusiveFromDpcLevel</a> routine. If the caller acquired the shared spin lock by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451053">ExAcquireSpinLockShared</a> routine, the caller should release the converted spin lock by calling the <a href="https://msdn.microsoft.com/D10C65A6-96E7-4BE0-BDD5-EFD129DC424C">ExReleaseSpinLockExclusive</a> routine, and the <i>OldIrql</i> value supplied as an input parameter to this routine should be the KIRQL value returned by <b>ExAcquireSpinLockShared</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451053">ExAcquireSpinLockShared</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451055">ExAcquireSpinLockSharedAtDpcLevel</a>



<a href="https://msdn.microsoft.com/D10C65A6-96E7-4BE0-BDD5-EFD129DC424C">ExReleaseSpinLockExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451058">ExReleaseSpinLockExclusiveFromDpcLevel</a>
 

 

