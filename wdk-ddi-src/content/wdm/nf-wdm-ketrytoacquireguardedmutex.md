---
UID: NF:wdm.KeTryToAcquireGuardedMutex
title: KeTryToAcquireGuardedMutex function
author: windows-driver-content
description: The KeTryToAcquireGuardedMutex routine acquires a guarded mutex, if available.
old-location: kernel\ketrytoacquireguardedmutex.htm
tech.root: kernel
ms.assetid: 5fa704ec-5068-42e9-8d52-2f775fd0e5c9
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeTryToAcquireGuardedMutex, KeTryToAcquireGuardedMutex routine [Kernel-Mode Driver Architecture], k105_4761d5a7-fc37-45de-a35e-7da9a99258b6.xml, kernel.ketrytoacquireguardedmutex, wdm/KeTryToAcquireGuardedMutex
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	KeTryToAcquireGuardedMutex
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

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554235">KGUARDED_MUTEX</a> structure for the guarded mutex.


## -returns



<b>KeTryToAcquireGuardedMutex</b> returns <b>TRUE</b> if the mutex is acquired, and <b>FALSE</b> otherwise.




## -remarks



Use <b>KeReleaseGuardedMutex</b> to release the mutex.

<b>KeTryToAcquireGuardedMutex</b> returns immediately, regardless of whether it can acquire the mutex. Use <b>KeAcquireGuardedMutex</b> to put the calling thread into a wait state until mutex becomes available.

A thread that calls <b>KeTryToAcquireGuardedMutex</b> implicitly enters a guarded region, where all APCs are disabled. They remain disabled until the thread releases the mutex with <b>KeReleaseGuardedMutex</b>.

For more information about guarded mutexes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545716">Fast Mutexes and Guarded Mutexes</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553124">KeReleaseGuardedMutex</a>
 

 

