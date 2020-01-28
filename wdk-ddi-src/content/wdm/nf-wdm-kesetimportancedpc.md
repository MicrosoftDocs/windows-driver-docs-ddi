---
UID: NF:wdm.KeSetImportanceDpc
title: KeSetImportanceDpc function (wdm.h)
description: The KeSetImportanceDpc routine specifies how soon the DPC routine is run.
old-location: kernel\kesetimportancedpc.htm
tech.root: kernel
ms.assetid: 0feb053b-6b58-4b26-8549-a6cf3996a3e6
ms.date: 04/30/2018
ms.keywords: KeSetImportanceDpc, KeSetImportanceDpc routine [Kernel-Mode Driver Architecture], k105_dc95afd2-5be3-4d48-a99f-0a9f2d8dab9b.xml, kernel.kesetimportancedpc, wdm/KeSetImportanceDpc
f1_keywords:
 - "wdm/KeSetImportanceDpc"
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeSetImportanceDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeSetImportanceDpc function


## -description


The <b>KeSetImportanceDpc</b> routine specifies how soon the DPC routine is run. 


## -parameters




### -param Dpc [in, out]

Pointer to the caller's DPC object, which <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a> already initialized. 


### -param Importance [in]

Specifies one of the following system-defined values to determine the behavior of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iorequestdpc">IoRequestDpc</a> when either routine is used to queue the DPC.





#### LowImportance

Place the DPC at the end of the DPC queue, and do not begin processing of the queue. 



#### MediumImportance

Place the DPC at the end of the DPC queue. If the DPC is assigned to the current processor's DPC queue, begin processing the queue immediately. <b>MediumImportance</b> is the default value for <i>Importance</i>. 



#### MediumHighImportance

Place the DPC at the end of the DPC queue, and begin processing the queue immediately. MediumHighImportance is available only on Windows Vista and later versions of Windows.



#### HighImportance

Place the DPC at the beginning of the DPC queue, and begin processing the queue immediately. 


##### - Importance.HighImportance

Place the DPC at the beginning of the DPC queue, and begin processing the queue immediately. 


##### - Importance.LowImportance

Place the DPC at the end of the DPC queue, and do not begin processing of the queue. 


##### - Importance.MediumHighImportance

Place the DPC at the end of the DPC queue, and begin processing the queue immediately. MediumHighImportance is available only on Windows Vista and later versions of Windows.


##### - Importance.MediumImportance

Place the DPC at the end of the DPC queue. If the DPC is assigned to the current processor's DPC queue, begin processing the queue immediately. <b>MediumImportance</b> is the default value for <i>Importance</i>. 


## -remarks



The <b>KeSetImportanceDpc</b> routine influences how soon a DPC is run after it is queued by determining:

<ul>
<li>
The location of the DPC within the DPC queue. Typically, the <b>KeInsertQueueDpc</b> and <b>IoRequestDpc</b> routines place a DPC at the end of the queue. If a driver first calls <b>KeSetImportanceDpc</b> with <i>Importance</i> = <b>HighImportance</b>, <b>KeInsertQueueDpc</b> and <b>IoRequestDpc</b> will place the DPC at the beginning of the queue.

</li>
<li>
When the system begins processing the DPC queue. Typically, <b>KeInsertQueueDpc</b> and <b>IoRequestDpc</b> immediately begin processing the DPC queue for the current processor. Drivers can specify different values for <i>Importance</i> to change this behavior.

</li>
</ul>
By default, DPCs are assigned to the DPC queue for the current processor, so specifying <b>MediumImportance</b> or <b>MediumHighImportance</b> for <i>Importance</i> has the same effect. However, drivers can use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesettargetprocessordpc">KeSetTargetProcessorDpc</a> to change the processor that the DPC will be assigned to.

For Windows Vista and later versions of the Windows operating system, you can use <b>KeSetImportanceDpc</b> for threaded DPCs. If the caller sets <i>Importance</i> to <b>HighImportance</b>, the DPC is placed at the beginning of the queue; otherwise, it is placed at the end. The routine does not affect when the threaded DPC queue is processed. Threaded DPCs are always processed by a dedicated thread at IRQL = PASSIVE_LEVEL. For more information about threaded DPCs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/threaded-dpcs">Threaded DPCs</a>.

Note that a driver must call <b>KeSetImportanceDpc</b> before it calls <b>KeInsertQueueDpc</b> and <b>IoRequestDpc</b> to have any effect.

For more information about how the system processes the DPC queue, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/organization-of-dpc-queues">Organization of DPC Queues</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iorequestdpc">IoRequestDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesettargetprocessordpc">KeSetTargetProcessorDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesynchronizeexecution">KeSynchronizeExecution</a>
 

 

