---
UID: NF:wdm.KeReleaseSpinLockFromDpcLevel
title: KeReleaseSpinLockFromDpcLevel macro
author: windows-driver-content
description: The KeReleaseSpinLockFromDpcLevel routine releases an executive spin lock without changing the IRQL.
old-location: kernel\kereleasespinlockfromdpclevel.htm
old-project: kernel
ms.assetid: 5f7a92ee-ebaf-442f-a197-2fb58dd65a25
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/KefReleaseSpinLockFromDpcLevel, KefReleaseSpinLockFromDpcLevel, KeReleaseSpinLockFromDpcLevel, k105_ed15a49d-6903-4f9f-914c-668242701b1e.xml, KeReleaseSpinLockFromDpcLevel routine [Kernel-Mode Driver Architecture], kernel.kereleasespinlockfromdpclevel, wdm/KeReleaseSpinLockFromDpcLevel
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
req.ddi-compliance: HwStorPortProhibitedDDIs, IrqlDispatch, SpinLockSafe
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeReleaseSpinLockFromDpcLevel
-	KefReleaseSpinLockFromDpcLevel
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeReleaseSpinLockFromDpcLevel macro


## -description


The <b>KeReleaseSpinLockFromDpcLevel</b> routine releases an executive spin lock without changing the IRQL.


## -syntax


````
VOID KeReleaseSpinLockFromDpcLevel(
  _Inout_ PKSPIN_LOCK SpinLock
);
````


## -parameters




### -param a

TBD






#### - SpinLock [in, out]

Pointer to an executive spin lock for which the caller provides the storage. 


## -remarks



Drivers call <b>KeReleaseSpinLockFromDpcLevel</b> to release a spin lock acquired by calling <a href="..\wdm\nf-wdm-keacquirespinlockatdpclevel.md">KeAcquireSpinLockAtDpcLevel</a>.

It is an error to call <b>KeReleaseSpinLockFromDpcLevel</b> if the specified spin lock was acquired by calling <a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a> because the caller's original IRQL is not restored, which can cause deadlocks or fatal page faults.

For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>. 




## -see-also

<a href="..\wdm\nf-wdm-keacquirespinlockatdpclevel.md">KeAcquireSpinLockAtDpcLevel</a>



<a href="..\wdm\nf-wdm-kereleasespinlock.md">KeReleaseSpinLock</a>



<a href="..\wdm\nf-wdm-keacquirespinlock.md">KeAcquireSpinLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeReleaseSpinLockFromDpcLevel routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

