---
UID: NF:wdm.KeTryToAcquireSpinLockAtDpcLevel
title: KeTryToAcquireSpinLockAtDpcLevel function
author: windows-driver-content
description: The KeTryToAcquireSpinLockAtDpcLevel routine attempts to acquire a spin lock at DISPATCH_LEVEL.
old-location: kernel\ketrytoacquirespinlockatdpclevel.htm
old-project: kernel
ms.assetid: b7791969-027e-4df7-b720-1eb612597c56
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeTryToAcquireSpinLockAtDpcLevel, KeTryToAcquireSpinLockAtDpcLevel routine [Kernel-Mode Driver Architecture], k105_416ac5db-d064-4ced-8cf8-311aca8dae7f.xml, kernel.ketrytoacquirespinlockatdpclevel, wdm/KeTryToAcquireSpinLockAtDpcLevel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: SpinLock, SpinlockRelease, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeTryToAcquireSpinLockAtDpcLevel
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeTryToAcquireSpinLockAtDpcLevel function


## -description


The <b>KeTryToAcquireSpinLockAtDpcLevel</b> routine attempts to acquire a spin lock at DISPATCH_LEVEL.


## -syntax


````
BOOLEAN KeTryToAcquireSpinLockAtDpcLevel(
  _Inout_ PKSPIN_LOCK SpinLock
);
````


## -parameters




### -param SpinLock [in, out]

Specifies the spin lock to acquire. The spin lock must have already been initialized by <a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>.


## -returns



<b>KeTryToAcquireSpinLockAtDpcLevel</b> returns <b>TRUE</b> if the spin lock has been acquired, and <b>FALSE</b> if the spin lock is already being held and cannot be acquired.




## -remarks



If the specified spin lock is not busy, the <b>KeTryToAcquireSpinLockAtDpcLevel</b> routine acquires the spin lock (see <a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a> for details) and returns <b>TRUE</b>. If the spin lock has already been acquired, the routine immediately returns <b>FALSE</b>.

If the spin lock is acquired, the caller can release it by using the <a href="..\wdm\nf-wdm-kereleasespinlock.md">KeReleaseSpinLock</a> routine.

If you want the driver to block when it is unable to acquire the spin lock, use <a href="..\wdm\nf-wdm-keacquirespinlockatdpclevel.md">KeAcquireSpinLockAtDpcLevel</a> instead.

For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.




## -see-also

<a href="..\wdm\nf-wdm-kereleasespinlock.md">KeReleaseSpinLock</a>



<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>



<a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a>



<a href="..\wdm\nf-wdm-keacquirespinlockatdpclevel.md">KeAcquireSpinLockAtDpcLevel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeTryToAcquireSpinLockAtDpcLevel routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

