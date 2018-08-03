---
UID: NF:wdm.KeReadStateTimer
title: KeReadStateTimer function
author: windows-driver-content
description: The KeReadStateTimer routine reads the current state of a timer object.
old-location: kernel\kereadstatetimer.htm
tech.root: kernel
ms.assetid: 0f7fc534-4a81-42e0-a3e6-8b91baa28b55
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeReadStateTimer, KeReadStateTimer routine [Kernel-Mode Driver Architecture], k105_8e101501-f419-40ff-91cd-a8aee0ffcbc8.xml, kernel.kereadstatetimer, wdm/KeReadStateTimer
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
req.ddi-compliance: IrqlKeDispatchLte, HwStorPortProhibitedDDIs
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
-	KeReadStateTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeReadStateTimer function


## -description


The <b>KeReadStateTimer</b> routine reads the current state of a timer object.


## -parameters




### -param Timer [in]

A pointer to an initialized timer object, for which the caller provides the storage.


## -returns



<b>KeReadStateTimer</b> returns <b>TRUE</b> if the current state of the timer object is signaled; otherwise, it returns <b>FALSE</b>.




## -remarks



This routine provides an efficient way to poll the signal state of a timer. <b>KeReadStateTimer</b> reads the state of the timer without synchronizing its access to the timer. Do not assume that accesses of a timer state by <b>KeReadStateTimer</b> are mutually exclusive of accesses by routines, such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff553286">KeSetTimer</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>, that do synchronize their access to the timer state.

For more information about timer objects, see <a href="https://msdn.microsoft.com/b58487de-6e9e-45f4-acb8-9233c8718ee2">Timer Objects and DPCs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554250">KTIMER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551970">KeCancelTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552168">KeInitializeTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553286">KeSetTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
 

 

