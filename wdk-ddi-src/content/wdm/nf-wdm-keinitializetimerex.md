---
UID: NF:wdm.KeInitializeTimerEx
title: KeInitializeTimerEx function
author: windows-driver-content
description: The KeInitializeTimerEx routine initializes an extended kernel timer object.
old-location: kernel\keinitializetimerex.htm
old-project: kernel
ms.assetid: 57ed4f33-6ce6-41ae-b424-147318ba7656
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeInitializeTimerEx, KeInitializeTimerEx routine [Kernel-Mode Driver Architecture], k105_62ca8d08-a87a-4cbd-80fa-18b646b8500d.xml, kernel.keinitializetimerex, wdm/KeInitializeTimerEx
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
-	KeInitializeTimerEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeInitializeTimerEx function


## -description


The <b>KeInitializeTimerEx</b> routine initializes an extended kernel timer object.


## -parameters




### -param Timer [out]

Pointer to a timer object, for which the caller provides the storage.


### -param Type [in]

Specifies the type of the timer object, either <b>NotificationTimer</b> or <b>SynchronizationTimer</b>.


## -returns



None




## -remarks



The timer object is initialized to a not-signaled state.

Storage for a timer object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

When a notification timer expires, all waiting threads are released and the timer remains in the signaled state until it is explicitly reset. When a synchronization timer expires, it is set to a signaled state until a single waiting thread is released and then the timer is reset to a not-signaled state.

Callers of <b>KeInitializeTimerEx</b> should be running at IRQL = DISPATCH_LEVEL or lower. It is best to initialize timers at IRQL = PASSIVE_LEVEL.

For more information about timer objects, see <a href="https://msdn.microsoft.com/b58487de-6e9e-45f4-acb8-9233c8718ee2">Timer Objects and DPCs</a>.

Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553286">KeSetTimer</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553292">KeSetTimerEx</a> to define when the timer will expire.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551970">KeCancelTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553099">KeReadStateTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553286">KeSetTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553292">KeSetTimerEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553324">KeWaitForMultipleObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
 

 

