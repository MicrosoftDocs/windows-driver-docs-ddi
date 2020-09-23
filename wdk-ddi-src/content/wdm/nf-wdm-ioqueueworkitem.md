---
UID: NF:wdm.IoQueueWorkItem
title: IoQueueWorkItem function (wdm.h)
description: The IoQueueWorkItem routine associates a WorkItem routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread.
old-location: kernel\ioqueueworkitem.htm
tech.root: kernel
ms.assetid: 92ec386e-205a-4704-bd13-941dd6d7d987
ms.date: 04/30/2018
keywords: ["IoQueueWorkItem function"]
ms.keywords: IoQueueWorkItem, IoQueueWorkItem routine [Kernel-Mode Driver Architecture], k104_6f5cb4e5-75d1-433a-864e-19de914aa2e7.xml, kernel.ioqueueworkitem, wdm/IoQueueWorkItem
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoQueueWorkItem
 - wdm/IoQueueWorkItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoQueueWorkItem
---

# IoQueueWorkItem function


## -description

The <b>IoQueueWorkItem</b> routine associates a <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine">WorkItem</a> routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread.

## -parameters

### -param IoWorkItem 

[in]
Pointer to an <a href="/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a> structure that was allocated by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a> or initialized by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeworkitem">IoInitializeWorkItem</a>.

### -param WorkerRoutine 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine">WorkItem</a> routine.

### -param QueueType 

[in]
Specifies a <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_work_queue_type">WORK_QUEUE_TYPE</a> value that stipulates the type of system worker thread to handle the work item. Drivers must specify <b>DelayedWorkQueue</b>.

### -param Context 

[in, optional]
Specifies driver-specific information for the work item. The system passes this value as the <i>Context</i> parameter to <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine">WorkItem</a>.

## -remarks

For more information about work items, see <a href="/windows-hardware/drivers/kernel/system-worker-threads">System Worker Threads</a>.

## -see-also

<a href="/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitemex">IoQueueWorkItemEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine">WorkItem</a>