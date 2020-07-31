---
UID: NF:wdm.KeReleaseGuardedMutex
title: KeReleaseGuardedMutex function (wdm.h)
description: The KeReleaseGuardedMutex routine releases a guarded mutex acquired with KeAcquireGuardedMutex or KeTryToAcquireGuardedMutex.
old-location: kernel\kereleaseguardedmutex.htm
tech.root: kernel
ms.assetid: 0734094d-0386-4b00-a2cb-881b782108dc
ms.date: 04/30/2018
keywords: ["KeReleaseGuardedMutex function"]
ms.keywords: KeReleaseGuardedMutex, KeReleaseGuardedMutex routine [Kernel-Mode Driver Architecture], k105_a338f1ba-027d-4637-a50f-776d60bd7da0.xml, kernel.kereleaseguardedmutex, wdm/KeReleaseGuardedMutex
f1_keywords:
 - "wdm/KeReleaseGuardedMutex"
 - "KeReleaseGuardedMutex"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeReleaseGuardedMutex
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# KeReleaseGuardedMutex function


## -description


The <b>KeReleaseGuardedMutex</b> routine releases a guarded mutex acquired with <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551892(v=vs.85)">KeAcquireGuardedMutex</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553307">KeTryToAcquireGuardedMutex</a>.


## -parameters




### -param Mutex [in, out]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KGUARDED_MUTEX</a> structure for the guarded mutex.


## -remarks



<b>KeReleaseGuardedMutex</b> implicitly exits the guarded region entered by <b>KeAcquireGuardedMutex</b> and <b>KeTryToAcquireGuardedMutex</b>.

For more information about guarded mutexes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes">Fast Mutexes and Guarded Mutexes</a>. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551892(v=vs.85)">KeAcquireGuardedMutex</a>
 

 

