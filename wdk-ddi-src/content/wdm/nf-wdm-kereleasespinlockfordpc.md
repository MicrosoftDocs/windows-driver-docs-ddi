---
UID: NF:wdm.KeReleaseSpinLockForDpc
title: KeReleaseSpinLockForDpc function
author: windows-driver-content
description: The KeReleaseSpinLockForDpc routine releases a spin lock that was acquired by calling KeAcquireSpinLockForDpc.
old-location: kernel\kereleasespinlockfordpc.htm
old-project: kernel
ms.assetid: b6b36720-0c56-46f6-bfa6-dd31fae7b6d4
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeReleaseSpinLockForDpc, KeReleaseSpinLockForDpc routine [Kernel-Mode Driver Architecture], k105_71e8daa4-ca71-41d9-bf2f-2866df1d0c9c.xml, kernel.kereleasespinlockfordpc, wdm/KeReleaseSpinLockForDpc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
-	KeReleaseSpinLockForDpc
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeReleaseSpinLockForDpc function


## -description


The <b>KeReleaseSpinLockForDpc</b> routine releases a spin lock that was acquired by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff551923">KeAcquireSpinLockForDpc</a>.


## -parameters




### -param SpinLock [in, out]

Pointer to the spin lock that <b>KeAcquireSpinLockForDpc</b> acquired.


### -param OldIrql [in]

Specifies the IRQL that was current when the spin lock was acquired. Specify the value returned by <b>KeAcquireSpinLockForDpc</b>.


## -returns



None




## -remarks



For more information about spin locks, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563830">Spin Locks</a>.

If <i>OldIrql</i> = PASSIVE_LEVEL, <b>KeReleaseSpinLockForDpc</b> lowers the current IRQL to PASSIVE_LEVEL. If <i>OldIrql</i> = DISPATCH_LEVEL, <b>KeReleaseSpinLockForDpc</b> does not change the current IRQL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551923">KeAcquireSpinLockForDpc</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeReleaseSpinLockForDpc routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

