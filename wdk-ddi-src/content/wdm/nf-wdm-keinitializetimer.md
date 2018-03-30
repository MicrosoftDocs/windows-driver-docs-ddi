---
UID: NF:wdm.KeInitializeTimer
title: KeInitializeTimer function
author: windows-driver-content
description: The KeInitializeTimer routine initializes a timer object.
old-location: kernel\keinitializetimer.htm
old-project: kernel
ms.assetid: 97140cf6-9c5a-4fdc-b7c7-10e6d28b9b1b
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeInitializeTimer, KeInitializeTimer routine [Kernel-Mode Driver Architecture], k105_ce90de5c-7259-4863-adf1-fe90f288e791.xml, kernel.keinitializetimer, wdm/KeInitializeTimer
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeInitializeTimer
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeInitializeTimer function


## -description


The <b>KeInitializeTimer</b> routine initializes a timer object.


## -parameters




### -param Timer [out]

Pointer to a timer object, for which the caller provides the storage.


## -returns



None




## -remarks



The timer object is initialized to a not-signaled state.

Storage for a timer object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

<b>KeInitializeTimer</b> can only initialize a notification timer. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff552173">KeInitializeTimerEx</a> to initialize a notification timer or a synchronization timer.

Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553286">KeSetTimer</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553292">KeSetTimerEx</a> to define when the timer will expire.

For more information about timer objects, see <a href="https://msdn.microsoft.com/b58487de-6e9e-45f4-acb8-9233c8718ee2">Timer Objects and DPCs</a>.

Callers of <b>KeInitializeTimer</b> should be running at IRQL = DISPATCH_LEVEL or lower. It is best to initialize timers at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551970">KeCancelTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552173">KeInitializeTimerEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553099">KeReadStateTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553286">KeSetTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553292">KeSetTimerEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553324">KeWaitForMultipleObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
 

 

