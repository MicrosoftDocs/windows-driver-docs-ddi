---
UID: NF:wdm.KeReleaseInterruptSpinLock
title: KeReleaseInterruptSpinLock function
author: windows-driver-content
description: The KeReleaseInterruptSpinLock routine releases an interrupt spin lock acquired by KeAcquireInterruptSpinLock.
old-location: kernel\kereleaseinterruptspinlock.htm
tech.root: kernel
ms.assetid: 291442df-21e1-4acf-a107-0a18f28e30ad
ms.date: 4/30/2018
ms.keywords: KeReleaseInterruptSpinLock, KeReleaseInterruptSpinLock routine [Kernel-Mode Driver Architecture], k105_673f3ed1-bb95-413b-b56b-e9fdea636e8f.xml, kernel.kereleaseinterruptspinlock, wdm/KeReleaseInterruptSpinLock
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
-	KeReleaseInterruptSpinLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeReleaseInterruptSpinLock function


## -description


The <b>KeReleaseInterruptSpinLock</b> routine releases an interrupt spin lock acquired by <a href="https://msdn.microsoft.com/library/windows/hardware/ff551914">KeAcquireInterruptSpinLock</a>.


## -parameters




### -param Interrupt [in, out]

Specifies the value of the <i>Interrupt</i> parameter passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551914">KeAcquireInterruptSpinLock</a>.


### -param OldIrql [in]

Specifies the IRQL value returned by <b>KeAcquireInterruptSpinLock</b>. 


## -returns



None




## -remarks



The <b>KeReleaseInterruptSpinLock</b> releases the interrupt spin lock, and lowers the IRQL value back to the <i>OldIrql</i> value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551914">KeAcquireInterruptSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553302">KeSynchronizeExecution</a>
 

 

