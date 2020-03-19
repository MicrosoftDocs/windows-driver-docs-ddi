---
UID: NF:wdm.IoUninitializeWorkItem
title: IoUninitializeWorkItem function (wdm.h)
description: The IoUninitializeWorkItem routine uninitializes a work item that was initialized by IoInitializeWorkItem.
old-location: kernel\iouninitializeworkitem.htm
tech.root: kernel
ms.assetid: 8e7713a5-534d-42b4-a719-7b7ce911245a
ms.date: 04/30/2018
keywords: ["IoUninitializeWorkItem function"]
ms.keywords: IoUninitializeWorkItem, IoUninitializeWorkItem routine [Kernel-Mode Driver Architecture], k104_05634a73-eb65-4572-a776-4dcd6b116f52.xml, kernel.iouninitializeworkitem, wdm/IoUninitializeWorkItem
f1_keywords:
 - "wdm/IoUninitializeWorkItem"
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
- IoUninitializeWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoUninitializeWorkItem function


## -description


The <b>IoUninitializeWorkItem</b> routine uninitializes a work item that was initialized by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeworkitem">IoInitializeWorkItem</a>.


## -parameters




### -param IoWorkItem [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a> structure to uninitialize. 


## -remarks



Only uninitialize a work item that is not currently queued. The system dequeues a work item before it runs the work item's callback routine, so <b>IoUninitializeWorkItem</b> can be called from within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine">WorkItem</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_workitem_routine_ex">WorkItemEx</a> routine for the work item.

For more information about work items, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-worker-threads">System Worker Threads</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeworkitem">IoInitializeWorkItem</a>
 

 

