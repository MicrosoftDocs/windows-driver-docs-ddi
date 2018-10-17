---
UID: NF:wdm.KeReleaseGuardedMutex
title: KeReleaseGuardedMutex function
author: windows-driver-content
description: The KeReleaseGuardedMutex routine releases a guarded mutex acquired with KeAcquireGuardedMutex or KeTryToAcquireGuardedMutex.
old-location: kernel\kereleaseguardedmutex.htm
tech.root: kernel
ms.assetid: 0734094d-0386-4b00-a2cb-881b782108dc
ms.date: 4/30/2018
ms.keywords: KeReleaseGuardedMutex, KeReleaseGuardedMutex routine [Kernel-Mode Driver Architecture], k105_a338f1ba-027d-4637-a50f-776d60bd7da0.xml, kernel.kereleaseguardedmutex, wdm/KeReleaseGuardedMutex
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeApcLte1, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeReleaseGuardedMutex
product:
-	Windows
targetos: Windows
req.typenames: 
---

# KeReleaseGuardedMutex function


## -description


The <b>KeReleaseGuardedMutex</b> routine releases a guarded mutex acquired with <a href="https://msdn.microsoft.com/library/windows/hardware/ff551892">KeAcquireGuardedMutex</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553307">KeTryToAcquireGuardedMutex</a>.


## -parameters




### -param Mutex [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554235">KGUARDED_MUTEX</a> structure for the guarded mutex.


## -returns



None




## -remarks



<b>KeReleaseGuardedMutex</b> implicitly exits the guarded region entered by <b>KeAcquireGuardedMutex</b> and <b>KeTryToAcquireGuardedMutex</b>.

For more information about guarded mutexes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545716">Fast Mutexes and Guarded Mutexes</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551892">KeAcquireGuardedMutex</a>
 

 

