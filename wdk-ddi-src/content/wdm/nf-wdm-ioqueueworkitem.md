---
UID: NF:wdm.IoQueueWorkItem
title: IoQueueWorkItem function
author: windows-driver-content
description: The IoQueueWorkItem routine associates a WorkItem routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread.
old-location: kernel\ioqueueworkitem.htm
old-project: kernel
ms.assetid: 92ec386e-205a-4704-bd13-941dd6d7d987
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoQueueWorkItem, IoQueueWorkItem routine [Kernel-Mode Driver Architecture], k104_6f5cb4e5-75d1-433a-864e-19de914aa2e7.xml, kernel.ioqueueworkitem, wdm/IoQueueWorkItem
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
req.ddi-compliance: 
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
-	IoQueueWorkItem
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoQueueWorkItem function


## -description


The <b>IoQueueWorkItem</b> routine associates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566380">WorkItem</a> routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread.


## -parameters




### -param IoWorkItem [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a> structure that was allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff548276">IoAllocateWorkItem</a> or initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549349">IoInitializeWorkItem</a>.


### -param WorkerRoutine [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566380">WorkItem</a> routine.


### -param QueueType [in]

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566382">WORK_QUEUE_TYPE</a> value that stipulates the type of system worker thread to handle the work item. Drivers must specify <b>DelayedWorkQueue</b>.


### -param Context [in, optional]

Specifies driver-specific information for the work item. The system passes this value as the <i>Context</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566380">WorkItem</a>.


## -returns



None.




## -remarks



For more information about work items, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548276">IoAllocateWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549474">IoQueueWorkItemEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566380">WorkItem</a>
 

 

