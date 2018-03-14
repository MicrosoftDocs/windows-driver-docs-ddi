---
UID: NF:wdm.KeInsertQueueDpc
title: KeInsertQueueDpc function
author: windows-driver-content
description: The KeInsertQueueDpc routine queues a DPC for execution.
old-location: kernel\keinsertqueuedpc.htm
old-project: kernel
ms.assetid: f1fc6880-23d1-4154-9305-4a918efd4a1d
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeInsertQueueDpc, KeInsertQueueDpc routine [Kernel-Mode Driver Architecture], k105_7f821e29-508f-4216-92db-a2e18c21d17c.xml, kernel.keinsertqueuedpc, wdm/KeInsertQueueDpc
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeInsertQueueDpc
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeInsertQueueDpc function


## -description


The <b>KeInsertQueueDpc</b> routine queues a DPC for execution. 


## -syntax


````
BOOLEAN KeInsertQueueDpc(
  _Inout_  PRKDPC Dpc,
  _In_opt_ PVOID  SystemArgument1,
  _In_opt_ PVOID  SystemArgument2
);
````


## -parameters




### -param Dpc [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure for the DPC object. This structure must have been initialized by either <a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a> or <a href="..\wdm\nf-wdm-keinitializethreadeddpc.md">KeInitializeThreadedDpc</a>.


### -param SystemArgument1 [in, optional]

Specifies driver-determined context data. This value is passed as the <i>SystemArgument1</i> parameter to the DPC object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a> routine. 


### -param SystemArgument2 [in, optional]

Specifies driver-determined context data. This value is passed as the <i>SystemArgument2</i> parameter to the DPC object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a> routine. 


## -returns



If the specified DPC object is not currently in a DPC queue, <b>KeInsertQueueDpc</b> queues the DPC and returns <b>TRUE</b>.




## -remarks



If the specified DPC object has already been queued, no operation is performed except to return <b>FALSE</b>. Otherwise, the DPC object is inserted in a DPC queue. For more information about DPC queues, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558754">Organization of DPC Queues</a>.

Note that a particular DPC object and the function that it represents can each be queued for execution only once at any particular time. 




## -see-also

<a href="..\wdm\nf-wdm-keremovequeuedpc.md">KeRemoveQueueDpc</a>



<a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a>



 

 


