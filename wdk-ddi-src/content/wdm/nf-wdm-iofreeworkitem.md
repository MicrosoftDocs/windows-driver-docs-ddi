---
UID: NF:wdm.IoFreeWorkItem
title: IoFreeWorkItem function (wdm.h)
description: The IoFreeWorkItem routine frees a work item that was allocated by IoAllocateWorkItem.
old-location: kernel\iofreeworkitem.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoFreeWorkItem function"]
ms.keywords: IoFreeWorkItem, IoFreeWorkItem routine [Kernel-Mode Driver Architecture], k104_7db57e08-0786-4f20-96d8-ecb7980a479c.xml, kernel.iofreeworkitem, wdm/IoFreeWorkItem
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
 - IoFreeWorkItem
 - wdm/IoFreeWorkItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoFreeWorkItem
---

# IoFreeWorkItem function


## -description

The <b>IoFreeWorkItem</b> routine frees a work item that was allocated by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a>.

## -parameters

### -param IoWorkItem 

[in]
Pointer to an <a href="/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a> structure that was returned by a previous call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a>.

## -remarks

Only free a work item that is not currently queued. The system dequeues a work item before it runs the work item's callback routine, so <b>IoFreeWorkItem</b> can be called from within the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine">WorkItem</a> or <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine_ex">WorkItemEx</a> routine for the work item. 

For more information about work items, see <a href="/windows-hardware/drivers/kernel/system-worker-threads">System Worker Threads</a>.

## -see-also

<a href="/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a>
