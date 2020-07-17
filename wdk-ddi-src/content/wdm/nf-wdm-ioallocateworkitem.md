---
UID: NF:wdm.IoAllocateWorkItem
title: IoAllocateWorkItem function (wdm.h)
description: The IoAllocateWorkItem routine allocates a work item.
old-location: kernel\ioallocateworkitem.htm
tech.root: kernel
ms.assetid: 950e31ff-2e8e-4dd3-9d6c-d3d86fd69472
ms.date: 04/30/2018
keywords: ["IoAllocateWorkItem function"]
ms.keywords: IoAllocateWorkItem, IoAllocateWorkItem routine [Kernel-Mode Driver Architecture], k104_6cb480b8-6cf9-4c68-953e-8a1c8153087a.xml, kernel.ioallocateworkitem, wdm/IoAllocateWorkItem
f1_keywords:
 - "wdm/IoAllocateWorkItem"
 - "IoAllocateWorkItem"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating system, and in Windows Me. This routine is not available in Windows 98.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoAllocateWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoAllocateWorkItem function


## -description


The <b>IoAllocateWorkItem</b> routine allocates a work item. 


## -parameters




### -param DeviceObject [in]

Pointer to the caller's driver object or to one of the caller's device objects. If the caller will later pass the work item to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a>, <i>DeviceObject</i> must point to a device object.


## -returns



<b>IoAllocateWorkItem</b> returns a pointer to the allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a> structure. The routine returns <b>NULL</b> if sufficient resources do not exist.




## -remarks



The driver must free the work item that is returned by <b>IoAllocateWorkItem</b> by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreeworkitem">IoFreeWorkItem</a>.

<b>IoAllocateWorkItem</b> both allocates and initializes a work item. A related routine, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeworkitem">IoInitializeWorkItem</a>, initializes a work item in storage that the driver has previously allocated. Do not call <b>IoInitializeWorkItem</b> to initialize a work item that was allocated by <b>IoAllocateWorkItem</b>.

For more information about work items, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-worker-threads">System Worker Threads</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreeworkitem">IoFreeWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeworkitem">IoInitializeWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitemex">IoQueueWorkItemEx</a>
 

 

