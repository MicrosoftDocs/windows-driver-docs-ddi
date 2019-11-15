---
UID: NF:wdm.IoInitializeWorkItem
title: IoInitializeWorkItem function (wdm.h)
description: The IoInitializeWorkItem routine initializes a work item that the caller has already allocated.
old-location: kernel\ioinitializeworkitem.htm
tech.root: kernel
ms.assetid: b7f4370e-75db-4238-8e23-9e48028a03f5
ms.date: 04/30/2018
ms.keywords: IoInitializeWorkItem, IoInitializeWorkItem routine [Kernel-Mode Driver Architecture], k104_06024bfe-5558-4039-a9b1-327895ba9b74.xml, kernel.ioinitializeworkitem, wdm/IoInitializeWorkItem
ms.topic: function
f1_keywords:
 - "wdm/IoInitializeWorkItem"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoInitializeWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoInitializeWorkItem function


## -description


The <b>IoInitializeWorkItem</b> routine initializes a work item that the caller has already allocated.


## -parameters




### -param IoObject [in]

Pointer to the caller's driver object or to one of the caller's device objects. If the caller will later pass the work item to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a>, <i>IoObject</i> must point to a device object.


### -param IoWorkItem [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a> structure to initialize.


## -remarks



The driver allocates its own storage for an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a> structure, and then calls <b>IoInitializeWorkItem</b> to initialize it. Memory must be allocated from nonpaged pool. To determine the number of bytes that is necessary to hold an <b>IO_WORKITEM</b> structure, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosizeofworkitem">IoSizeofWorkItem</a>.

An <b>IO_WORKITEM</b> structure that is initialized by <b>IoInitializeWorkItem</b> <u>must</u> be uninitialized by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iouninitializeworkitem">IoUninitializeWorkItem</a> before it is freed.

A related routine, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a>, both allocates and initializes a work item. By combining allocation and initialization into a single call, <b>IoAllocateWorkItem</b> might be more convenient for some drivers to use than <b>IoInitializeWorkItem</b>, which does initialization only. However, <b>IoInitializeWorkItem</b> is required by drivers that must initialize work items in previously allocated storage.

For example, a driver might allocate a block of storage for a pool of work items. The driver can call <b>IoInitializeWorkItem</b> to initialize a work item when the work item is allocated from the pool. The driver can call <b>IoUninitializeWorkItem</b> to uninitialize the work item when it is returned to the pool. During the initial storage allocation for the pool, the driver can call <b>IoSizeofWorkitem</b> to determine how much storage to allocate for each work item.

For more information about work items, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-worker-threads">System Worker Threads</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateworkitem">IoAllocateWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitem">IoQueueWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioqueueworkitemex">IoQueueWorkItemEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosizeofworkitem">IoSizeofWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iouninitializeworkitem">IoUninitializeWorkItem</a>
 

 

