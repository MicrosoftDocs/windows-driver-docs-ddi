---
UID: NF:wdm.KeInsertQueueDpc
title: KeInsertQueueDpc function (wdm.h)
description: The KeInsertQueueDpc routine queues a DPC for execution.
old-location: kernel\keinsertqueuedpc.htm
tech.root: kernel
ms.assetid: f1fc6880-23d1-4154-9305-4a918efd4a1d
ms.date: 04/30/2018
ms.keywords: KeInsertQueueDpc, KeInsertQueueDpc routine [Kernel-Mode Driver Architecture], k105_7f821e29-508f-4216-92db-a2e18c21d17c.xml, kernel.keinsertqueuedpc, wdm/KeInsertQueueDpc
f1_keywords:
 - "wdm/KeInsertQueueDpc"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: MarkingQueuedIrps, HwStorPortProhibitedDDIs
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
- KeInsertQueueDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeInsertQueueDpc function


## -description


The <b>KeInsertQueueDpc</b> routine queues a DPC for execution. 


## -parameters




### -param Dpc [in, out]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a> structure for the DPC object. This structure must have been initialized by either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializethreadeddpc">KeInitializeThreadedDpc</a>.


### -param SystemArgument1 [in, optional]

Specifies driver-determined context data. This value is passed as the <i>SystemArgument1</i> parameter to the DPC object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kdeferred_routine">CustomDpc</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a> routine. 


### -param SystemArgument2 [in, optional]

Specifies driver-determined context data. This value is passed as the <i>SystemArgument2</i> parameter to the DPC object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kdeferred_routine">CustomDpc</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a> routine. 


## -returns



If the specified DPC object is not currently in a DPC queue, <b>KeInsertQueueDpc</b> queues the DPC and returns <b>TRUE</b>.




## -remarks



If the specified DPC object has already been queued, no operation is performed except to return <b>FALSE</b>. Otherwise, the DPC object is inserted in a DPC queue. For more information about DPC queues, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/organization-of-dpc-queues">Organization of DPC Queues</a>.

Note that a particular DPC object and the function that it represents can each be queued for execution only once at any particular time. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kdeferred_routine">CustomDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keremovequeuedpc">KeRemoveQueueDpc</a>
 

 

