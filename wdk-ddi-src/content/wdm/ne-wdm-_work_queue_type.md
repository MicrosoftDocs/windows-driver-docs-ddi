---
UID: NE:wdm._WORK_QUEUE_TYPE
title: "_WORK_QUEUE_TYPE" (wdm.h)
description: The WORK_QUEUE_TYPE enumeration type indicates the type of system worker thread that handles a work item.
old-location: kernel\work_queue_type.htm
tech.root: kernel
ms.assetid: 5bbebf1f-ca0f-44b7-a5cd-f06b637aa3de
ms.date: 04/30/2018
ms.keywords: BackgroundWorkQueue, CriticalWorkQueue, CustomPriorityWorkQueue, DelayedWorkQueue, HyperCriticalWorkQueue, MaximumWorkQueue, NormalWorkQueue, RealTimeWorkQueue, SuperCriticalWorkQueue, WORK_QUEUE_TYPE, WORK_QUEUE_TYPE enumeration [Kernel-Mode Driver Architecture], _WORK_QUEUE_TYPE, kernel.work_queue_type, sysenum_5bc5bb84-a8c7-46af-982e-37b8ec51723f.xml, wdm/BackgroundWorkQueue, wdm/CriticalWorkQueue, wdm/CustomPriorityWorkQueue, wdm/DelayedWorkQueue, wdm/HyperCriticalWorkQueue, wdm/MaximumWorkQueue, wdm/NormalWorkQueue, wdm/RealTimeWorkQueue, wdm/SuperCriticalWorkQueue, wdm/WORK_QUEUE_TYPE
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	WORK_QUEUE_TYPE
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
---

# _WORK_QUEUE_TYPE enumeration


## -description


The <b>WORK_QUEUE_TYPE</b> enumeration type indicates the type of system worker thread that handles a work item.


## -enum-fields




### -field CriticalWorkQueue

Indicates a real-time system worker thread. The assigned priority level is 13.


### -field DelayedWorkQueue

Indicates an ordinary worker thread. The assigned priority level is 12.


### -field HyperCriticalWorkQueue

System  priority level. The assigned priority level is 15.


### -field NormalWorkQueue

System priority level. The assigned priority level is 8


### -field BackgroundWorkQueue

System priority level. The assigned priority level is 7.


### -field RealTimeWorkQueue

System  priority level. The assigned priority level is18.


### -field SuperCriticalWorkQueue

System  priority level. The assigned priority level is 14.


### -field MaximumWorkQueue

System  priority maximum. No priority level assigned.


### -field CustomPriorityWorkQueue

The queue has a custom priority level assigned by the caller. The <b>CustomPriorityWorkQueue</b> value is the base priority level for the custom priority queue. Work items are queued at a particular priority by setting <i>QueueType</i> to <b>CustomPriorityWorkQueue</b> + <i>Priority</i> where <i>Priority</i> is the <b>KPRIORITY</b> value for the work item.

This queue type is valid starting with Windows 8.1.


## -remarks



For drivers targeting Windows 8.1 or later versions of Windows, use of only <b>CustomPriorityWorkQueue</b> with a custom priority level is recommended.

 A work queue priority &lt; 17 is advised since queuing  
    at a higher priority may interfere with work item processing by critical system components.

For more information about system worker threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549466">IoQueueWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549474">IoQueueWorkItemEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn683917">IoTryQueueWorkItem</a>
 

 

