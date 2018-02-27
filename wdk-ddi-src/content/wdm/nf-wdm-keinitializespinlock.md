---
UID: NF:wdm.KeInitializeSpinLock
title: KeInitializeSpinLock function
author: windows-driver-content
description: The KeInitializeSpinLock routine initializes a variable of type KSPIN_LOCK.
old-location: kernel\keinitializespinlock.htm
old-project: kernel
ms.assetid: 84962db0-55ed-443c-84e3-2d8f3e9ec1d7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeInitializeSpinLock, KeInitializeSpinLock routine [Kernel-Mode Driver Architecture], k105_715eff59-827a-4d41-8e3a-2ce0d1f1181d.xml, kernel.keinitializespinlock, wdm/KeInitializeSpinLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeInitializeSpinLock
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeInitializeSpinLock function


## -description


The <b>KeInitializeSpinLock </b>routine initializes a variable of type KSPIN_LOCK.


## -syntax


````
VOID KeInitializeSpinLock(
  _Out_ PKSPIN_LOCK SpinLock
);
````


## -parameters




### -param SpinLock [out]

Pointer to a spin lock, for which the caller must provide the storage.


## -returns



None




## -remarks



This routine must be called before an initial call to <a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a>, to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551899">KeAcquireInStackQueuedSpinLock</a>, or to any other support routine that requires a spin lock as an argument.

Storage for a spin lock object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.

Callers of this routine can be running at any IRQL. Usually, a caller is running at IRQL = PASSIVE_LEVEL in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551908">KeAcquireInStackQueuedSpinLockAtDpcLevel</a>



<a href="..\wdm\nf-wdm-kereleasespinlockfromdpclevel.md">KeReleaseSpinLockFromDpcLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553130">KeReleaseInStackQueuedSpinLock</a>



<a href="..\wdm\nf-wdm-kereleasespinlock.md">KeReleaseSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553137">KeReleaseInStackQueuedSpinLockFromDpcLevel</a>



<a href="..\wdm\nf-wdm-keacquirespinlockatdpclevel.md">KeAcquireSpinLockAtDpcLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551899">KeAcquireInStackQueuedSpinLock</a>



<a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeInitializeSpinLock routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

