---
UID: NF:wdm.KeCancelTimer
title: KeCancelTimer function
author: windows-driver-content
description: The KeCancelTimer routine dequeues a timer object before the timer interval, if any was set, expires.
old-location: kernel\kecanceltimer.htm
tech.root: kernel
ms.assetid: aefbf6d6-c107-4bf2-993d-d7ba8ea7ffcd
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeCancelTimer, KeCancelTimer routine [Kernel-Mode Driver Architecture], k105_89adf0ea-9f6b-4e21-be3a-7f75f1baec10.xml, kernel.kecanceltimer, wdm/KeCancelTimer
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
-	KeCancelTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeCancelTimer function


## -description


The <b>KeCancelTimer</b> routine dequeues a timer object before the timer interval, if any was set, expires.


## -parameters




### -param Arg1 [in, out]

Pointer to an initialized timer object, for which the caller provides the storage.




## -returns



If the specified timer object is in the system timer queue, <b>KeCancelTimer</b> returns <b>TRUE</b>.




## -remarks



If the timer object is currently in the system timer queue, it is removed from the queue. If a DPC object is associated with the timer, it too is canceled. Otherwise, no operation is performed.

The routine returns <b>TRUE</b> if the timer is still in the timer queue. A nonperiodic timer is removed from the system queue as soon as it expires. Thus, for nonperiodic timers, <b>KeCancelTimer</b> returns <b>FALSE</b> if the timer DPC has been queued. Periodic timers are always in the timer queue, so <b>KeCancelTimer</b> always returns <b>TRUE</b> for periodic timers. 

Note that a DPC that is already running runs to completion. The driver must ensure that the DPC has completed before freeing any resources used by the DPC. For a nonperiodic timer, you can use synchronization primitives, such as event objects, to synchronize between the driver and the DPC. The driver can check the return code of <b>KeCancelTimer</b> to determine if the DPC is running. If so, the DPC can signal the event before exiting, and the driver can wait for that event to be reset to the not-signaled state.

Since for periodic timers <b>KeCancelTimer</b> always returns <b>TRUE</b>, drivers must use a different technique to wait until the DPC has completed. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552050">KeFlushQueuedDpcs</a> routine to block until the DPC executes.

Drivers do not need to synchronize for data stored in global variables or driver object extensions. The system automatically calls <b>KeFlushQueuedDpcs</b> before deallocating either of these regions.

For more information about timer objects, see <a href="https://msdn.microsoft.com/b58487de-6e9e-45f4-acb8-9233c8718ee2">Timer Objects and DPCs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552168">KeInitializeTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553099">KeReadStateTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553286">KeSetTimer</a>
 

 

