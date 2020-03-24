---
UID: NF:wdm.KeReleaseSpinLockForDpc
title: KeReleaseSpinLockForDpc function (wdm.h)
description: The KeReleaseSpinLockForDpc routine releases a spin lock that was acquired by calling KeAcquireSpinLockForDpc.
old-location: kernel\kereleasespinlockfordpc.htm
tech.root: kernel
ms.assetid: b6b36720-0c56-46f6-bfa6-dd31fae7b6d4
ms.date: 04/30/2018
keywords: ["KeReleaseSpinLockForDpc function"]
ms.keywords: KeReleaseSpinLockForDpc, KeReleaseSpinLockForDpc routine [Kernel-Mode Driver Architecture], k105_71e8daa4-ca71-41d9-bf2f-2866df1d0c9c.xml, kernel.kereleasespinlockfordpc, wdm/KeReleaseSpinLockForDpc
f1_keywords:
 - "wdm/KeReleaseSpinLockForDpc"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeReleaseSpinLockForDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeReleaseSpinLockForDpc function


## -description


The <b>KeReleaseSpinLockForDpc</b> routine releases a spin lock that was acquired by calling <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551923(v=vs.85)">KeAcquireSpinLockForDpc</a>.


## -parameters




### -param SpinLock [in, out]

Pointer to the spin lock that <b>KeAcquireSpinLockForDpc</b> acquired.


### -param OldIrql [in]

Specifies the IRQL that was current when the spin lock was acquired. Specify the value returned by <b>KeAcquireSpinLockForDpc</b>.


## -remarks



For more information about spin locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/spin-locks">Spin Locks</a>.

If <i>OldIrql</i> = PASSIVE_LEVEL, <b>KeReleaseSpinLockForDpc</b> lowers the current IRQL to PASSIVE_LEVEL. If <i>OldIrql</i> = DISPATCH_LEVEL, <b>KeReleaseSpinLockForDpc</b> does not change the current IRQL.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551923(v=vs.85)">KeAcquireSpinLockForDpc</a>
 

 

