---
UID: NF:wdm.KeReadStateMutex
title: KeReadStateMutex function
author: windows-driver-content
description: The KeReadStateMutex routine returns the current state, signaled or not-signaled, of the specified mutex object.
old-location: kernel\kereadstatemutex.htm
old-project: kernel
ms.assetid: b23d846a-a1d4-4b2a-ab3c-8076302ff3fc
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeReadStateMutex, KeReadStateMutex routine [Kernel-Mode Driver Architecture], k105_37175048-e4ee-4b79-93f3-013195192b4c.xml, kernel.kereadstatemutex, wdm/KeReadStateMutex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeReadStateMutex
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeReadStateMutex function


## -description


The <b>KeReadStateMutex</b> routine returns the current state, signaled or not-signaled, of the specified mutex object.


## -parameters




### -param Mutex [in]

Pointer to an initialized mutex object for which the caller provides the storage.


## -returns



If the return value is 1, the state of the mutex object is signaled.




## -remarks



This routine provides an efficient way to poll the signal state of a mutex. <b>KeReadStateMutex</b> reads the state of the mutex without synchronizing its access to the mutex. Do not assume that accesses of a mutex state by <b>KeReadStateMutex</b> are mutually exclusive of accesses by routines, such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff553140">KeReleaseMutex</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>, that do synchronize their access to the mutex state.

For more information about mutex objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556417">Mutex Objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545293">ExInitializeFastMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552147">KeInitializeMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553140">KeReleaseMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
 

 

