---
UID: NF:wdm.IoQueueWorkItemEx
title: IoQueueWorkItemEx function
author: windows-driver-content
description: The IoQueueWorkItemEx routine associates a WorkItemEx routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread.
old-location: kernel\ioqueueworkitemex.htm
old-project: kernel
ms.assetid: 277a6e13-dc2d-4170-a141-9df5b93eb504
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoQueueWorkItemEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoQueueWorkItemEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoQueueWorkItemEx function



## -description
The <b>IoQueueWorkItemEx</b> routine associates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566381">WorkItemEx</a> routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread.



## -syntax

````
VOID IoQueueWorkItemEx(
  _In_     PIO_WORKITEM            IoWorkItem,
  _In_     PIO_WORKITEM_ROUTINE_EX WorkerRoutine,
  _In_     WORK_QUEUE_TYPE         QueueType,
  _In_opt_ PVOID                   Context
);
````


## -parameters

### -param IoWorkItem [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a> structure that was allocated by <a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a> or initialized by <a href="..\wdm\nf-wdm-ioinitializeworkitem.md">IoInitializeWorkItem</a>. 


### -param WorkerRoutine [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566381">WorkItemEx</a> routine. 


### -param QueueType [in]

Specifies a <a href="..\wdm\ne-wdm-_work_queue_type.md">WORK_QUEUE_TYPE</a> value that stipulates the type of system worker thread to handle the work item. Drivers must specify <b>DelayedWorkQueue</b>.


### -param Context [in, optional]

Specifies driver-specific information for the work item. The system passes this value as the <i>Context</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566381">WorkItemEx</a>.


## -returns
None


## -remarks
For more information about work items, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioinitializeworkitem.md">IoInitializeWorkItem</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566381">WorkItemEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoQueueWorkItemEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

