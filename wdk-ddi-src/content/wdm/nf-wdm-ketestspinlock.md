---
UID: NF:wdm.KeTestSpinLock
title: KeTestSpinLock function
author: windows-driver-content
description: The KeTestSpinLock routine tests for the availability of a spin lock.
old-location: kernel\ketestspinlock.htm
old-project: kernel
ms.assetid: 5386349c-b4b8-43db-8f66-70dc7e71345e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeTestSpinLock, KeTestSpinLock routine [Kernel-Mode Driver Architecture], k105_99f18fd9-0242-4939-86ab-016236f9adcb.xml, kernel.ketestspinlock, wdm/KeTestSpinLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
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
-	KeTestSpinLock
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeTestSpinLock function


## -description


The <b>KeTestSpinLock</b> routine tests for the availability of a spin lock.


## -syntax


````
BOOLEAN KeTestSpinLock(
  _In_ PKSPIN_LOCK SpinLock
);
````


## -parameters




### -param SpinLock [in]

A pointer to a spin lock. The spin lock must have been initialized by calling <a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>.


## -returns



<b>KeTestSpinLock</b> returns <b>FALSE</b> if the spin lock is currently being held. Otherwise, it returns <b>TRUE</b>.




## -remarks



This routine enables the caller that is running at a low IRQL to test the spin lock. If <b>KeTestSpinLock</b> returns <b>TRUE</b>, the caller can try to acquire the spin lock with a high probability of immediate success.

This routine neither raises nor lowers the IRQL, and it never acquires the spin lock.

For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.




## -see-also

<a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a>



<a href="..\wdm\nf-wdm-kereleasespinlock.md">KeReleaseSpinLock</a>



<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeTestSpinLock routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

