---
UID: NE:wdm._WORK_QUEUE_TYPE
title: "_WORK_QUEUE_TYPE"
author: windows-driver-content
description: The WORK_QUEUE_TYPE enumeration type indicates the type of system worker thread that handles a work item.
old-location: kernel\work_queue_type.htm
old-project: kernel
ms.assetid: 5bbebf1f-ca0f-44b7-a5cd-f06b637aa3de
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: WORK_QUEUE_TYPE, wdm/RealTimeWorkQueue, sysenum_5bc5bb84-a8c7-46af-982e-37b8ec51723f.xml, CriticalWorkQueue, HyperCriticalWorkQueue, WORK_QUEUE_TYPE enumeration [Kernel-Mode Driver Architecture], RealTimeWorkQueue, SuperCriticalWorkQueue, wdm/NormalWorkQueue, _WORK_QUEUE_TYPE, wdm/BackgroundWorkQueue, MaximumWorkQueue, kernel.work_queue_type, wdm/HyperCriticalWorkQueue, wdm/DelayedWorkQueue, wdm/MaximumWorkQueue, CustomPriorityWorkQueue, wdm/CriticalWorkQueue, wdm/CustomPriorityWorkQueue, wdm/WORK_QUEUE_TYPE, NormalWorkQueue, DelayedWorkQueue, BackgroundWorkQueue, wdm/SuperCriticalWorkQueue
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	WORK_QUEUE_TYPE
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# _WORK_QUEUE_TYPE enumeration


## -description


The <b>WORK_QUEUE_TYPE</b> enumeration type indicates the type of system worker thread that handles a work item.


## -syntax


````
typedef enum _WORK_QUEUE_TYPE { 
  CriticalWorkQueue,
  DelayedWorkQueue,
  HyperCriticalWorkQueue,
  NormalWorkQueue,
  BackgroundWorkQueue,
  RealTimeWorkQueue,
  SuperCriticalWorkQueue,
  MaximumWorkQueue,
  CustomPriorityWorkQueue  = 32
} WORK_QUEUE_TYPE;
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/dn683917">IoTryQueueWorkItem</a>



<a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a>



<a href="..\wdm\nf-wdm-ioqueueworkitemex.md">IoQueueWorkItemEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WORK_QUEUE_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

