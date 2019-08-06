---
UID: NF:wdm.KeInitializeGuardedMutex
title: KeInitializeGuardedMutex function (wdm.h)
description: The KeInitializeGuardedMutex routine initializes a guarded mutex.
old-location: kernel\keinitializeguardedmutex.htm
tech.root: kernel
ms.assetid: 28d45b36-c20d-40a5-bdf9-5fb754e36e74
ms.date: 04/30/2018
ms.keywords: KeInitializeGuardedMutex, KeInitializeGuardedMutex routine [Kernel-Mode Driver Architecture], k105_e9686411-583c-43bb-b7e6-b5248bed72f8.xml, kernel.keinitializeguardedmutex, wdm/KeInitializeGuardedMutex
ms.topic: function
f1_keywords:
 - "wdm/KeInitializeGuardedMutex"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 with Service Pack 1 (SP1) and later versions of Windows.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeInitializeGuardedMutex
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeInitializeGuardedMutex function


## -description


The <b>KeInitializeGuardedMutex</b> routine initializes a guarded mutex. 


## -parameters




### -param Mutex [out]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KGUARDED_MUTEX</a> structure to initialize. The storage must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms.


## -returns



None




## -remarks



Guarded mutexes must be allocated from nonpaged pool.

For more information about guarded mutexes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes">Fast Mutexes and Guarded Mutexes</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KGUARDED_MUTEX</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551892(v=vs.85)">KeAcquireGuardedMutex</a>
 

 

