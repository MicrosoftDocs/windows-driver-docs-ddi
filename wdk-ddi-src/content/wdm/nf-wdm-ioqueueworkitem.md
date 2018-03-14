---
UID: NF:wdm.IoQueueWorkItem
title: IoQueueWorkItem function
author: windows-driver-content
description: The IoQueueWorkItem routine associates a WorkItem routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread.
old-location: kernel\ioqueueworkitem.htm
old-project: kernel
ms.assetid: 92ec386e-205a-4704-bd13-941dd6d7d987
ms.author: windowsdriverdev
ms.date: 3/1/2018
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


## -syntax


````
VOID IoQueueWorkItem(
  _In_     PIO_WORKITEM         IoWorkItem,
  _In_     PIO_WORKITEM_ROUTINE WorkerRoutine,
  _In_     WORK_QUEUE_TYPE      QueueType,
  _In_opt_ PVOID                Context
);
````


## -parameters




### -param IoWorkItem [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a> structure that was allocated by <a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a> or initialized by <a href="..\wdm\nf-wdm-ioinitializeworkitem.md">IoInitializeWorkItem</a>.


### -param WorkerRoutine [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566380">WorkItem</a> routine.


### -param QueueType [in]

Specifies a <a href="..\wdm\ne-wdm-_work_queue_type.md">WORK_QUEUE_TYPE</a> value that stipulates the type of system worker thread to handle the work item. Drivers must specify <b>DelayedWorkQueue</b>.


### -param Context [in, optional]

Specifies driver-specific information for the work item. The system passes this value as the <i>Context</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566380">WorkItem</a>.


## -returns



None.




## -remarks



For more information about work items, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566380">WorkItem</a>



<a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a>



<a href="..\wdm\nf-wdm-ioqueueworkitemex.md">IoQueueWorkItemEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoQueueWorkItem routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

