---
UID: NF:wdm.KeTryToAcquireGuardedMutex
title: KeTryToAcquireGuardedMutex function (wdm.h)
description: The KeTryToAcquireGuardedMutex routine acquires a guarded mutex, if available.
old-location: kernel\ketrytoacquireguardedmutex.htm
tech.root: kernel
ms.assetid: 5fa704ec-5068-42e9-8d52-2f775fd0e5c9
ms.date: 04/30/2018
ms.keywords: KeTryToAcquireGuardedMutex, KeTryToAcquireGuardedMutex routine [Kernel-Mode Driver Architecture], k105_4761d5a7-fc37-45de-a35e-7da9a99258b6.xml, kernel.ketrytoacquireguardedmutex, wdm/KeTryToAcquireGuardedMutex
ms.topic: function
f1_keywords:
 - "wdm/KeTryToAcquireGuardedMutex"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeTryToAcquireGuardedMutex
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeTryToAcquireGuardedMutex function


## -description


The <b>KeTryToAcquireGuardedMutex</b> routine acquires a guarded mutex, if available.


## -parameters




### -param Mutex [in, out]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KGUARDED_MUTEX</a> structure for the guarded mutex.


## -returns



<b>KeTryToAcquireGuardedMutex</b> returns <b>TRUE</b> if the mutex is acquired, and <b>FALSE</b> otherwise.




## -remarks



Use <b>KeReleaseGuardedMutex</b> to release the mutex.

<b>KeTryToAcquireGuardedMutex</b> returns immediately, regardless of whether it can acquire the mutex. Use <b>KeAcquireGuardedMutex</b> to put the calling thread into a wait state until mutex becomes available.

A thread that calls <b>KeTryToAcquireGuardedMutex</b> implicitly enters a guarded region, where all APCs are disabled. They remain disabled until the thread releases the mutex with <b>KeReleaseGuardedMutex</b>.

For more information about guarded mutexes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes">Fast Mutexes and Guarded Mutexes</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kereleaseguardedmutex">KeReleaseGuardedMutex</a>
 

 

