---
UID: NF:wdm.KeTestSpinLock
title: KeTestSpinLock function (wdm.h)
description: The KeTestSpinLock routine tests for the availability of a spin lock.
old-location: kernel\ketestspinlock.htm
tech.root: kernel
ms.assetid: 5386349c-b4b8-43db-8f66-70dc7e71345e
ms.date: 04/30/2018
keywords: ["KeTestSpinLock function"]
ms.keywords: KeTestSpinLock, KeTestSpinLock routine [Kernel-Mode Driver Architecture], k105_99f18fd9-0242-4939-86ab-016236f9adcb.xml, kernel.ketestspinlock, wdm/KeTestSpinLock
f1_keywords:
 - "wdm/KeTestSpinLock"
 - "KeTestSpinLock"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeTestSpinLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeTestSpinLock function


## -description


The <b>KeTestSpinLock</b> routine tests for the availability of a spin lock.


## -parameters




### -param SpinLock [in]

A pointer to a spin lock. The spin lock must have been initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>.


## -returns



<b>KeTestSpinLock</b> returns <b>FALSE</b> if the spin lock is currently being held. Otherwise, it returns <b>TRUE</b>.




## -remarks



This routine enables the caller that is running at a low IRQL to test the spin lock. If <b>KeTestSpinLock</b> returns <b>TRUE</b>, the caller can try to acquire the spin lock with a high probability of immediate success.

This routine neither raises nor lowers the IRQL, and it never acquires the spin lock.

For more information about spin locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/spin-locks">Spin Locks</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializespinlock">KeInitializeSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereleasespinlock">KeReleaseSpinLock</a>
 

 

