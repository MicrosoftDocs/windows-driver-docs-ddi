---
UID: NF:wdm.KeTryToAcquireSpinLockAtDpcLevel
title: KeTryToAcquireSpinLockAtDpcLevel function (wdm.h)
description: The KeTryToAcquireSpinLockAtDpcLevel routine attempts to acquire a spin lock at DISPATCH_LEVEL.
old-location: kernel\ketrytoacquirespinlockatdpclevel.htm
tech.root: kernel
ms.assetid: b7791969-027e-4df7-b720-1eb612597c56
ms.date: 04/30/2018
keywords: ["KeTryToAcquireSpinLockAtDpcLevel function"]
ms.keywords: KeTryToAcquireSpinLockAtDpcLevel, KeTryToAcquireSpinLockAtDpcLevel routine [Kernel-Mode Driver Architecture], k105_416ac5db-d064-4ced-8cf8-311aca8dae7f.xml, kernel.ketrytoacquirespinlockatdpclevel, wdm/KeTryToAcquireSpinLockAtDpcLevel
f1_keywords:
 - "wdm/KeTryToAcquireSpinLockAtDpcLevel"
 - "KeTryToAcquireSpinLockAtDpcLevel"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeTryToAcquireSpinLockAtDpcLevel
targetos: Windows
req.typenames: 
---

# KeTryToAcquireSpinLockAtDpcLevel function


## -description


The <b>KeTryToAcquireSpinLockAtDpcLevel</b> routine attempts to acquire a spin lock at DISPATCH_LEVEL.


## -parameters




### -param SpinLock 
[in, out]
Specifies the spin lock to acquire. The spin lock must have already been initialized by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>.


## -returns



<b>KeTryToAcquireSpinLockAtDpcLevel</b> returns <b>TRUE</b> if the spin lock has been acquired, and <b>FALSE</b> if the spin lock is already being held and cannot be acquired.




## -remarks



If the specified spin lock is not busy, the <b>KeTryToAcquireSpinLockAtDpcLevel</b> routine acquires the spin lock (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a> for details) and returns <b>TRUE</b>. If the spin lock has already been acquired, the routine immediately returns <b>FALSE</b>.

If the spin lock is acquired, the caller can release it by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereleasespinlock">KeReleaseSpinLock</a> routine.

If you want the driver to block when it is unable to acquire the spin lock, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlockatdpclevel">KeAcquireSpinLockAtDpcLevel</a> instead.

For more information about spin locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/spin-locks">Spin Locks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlockatdpclevel">KeAcquireSpinLockAtDpcLevel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereleasespinlock">KeReleaseSpinLock</a>
 

 

