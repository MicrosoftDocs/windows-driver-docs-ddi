---
UID: NC:storport.HW_WORKITEM
title: HW_WORKITEM (storport.h)
description: A miniport-provided callback function for processing a Storport work item request.
old-location: storage\hwstorworkitem.htm
tech.root: storage
ms.assetid: CBBB1350-66BE-4F74-A0CE-0400245352F3
ms.date: 03/29/2018
ms.keywords: HW_WORKITEM, HwStorWorkItem, HwStorWorkItem routine [Storage Devices], storage.hwstorworkitem, storport/HwStorWorkItem
ms.topic: callback
f1_keywords:
 - "storport/HwStorWorkItem"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- storport.h
api_name:
- HwStorWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# HW_WORKITEM callback function


## -description


A miniport-provided callback function for processing a Storport work item request.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the miniport driver's per-HBA storage area. 


### -param Context [in, optional]

Optional context provided by the miniport in the <i>Callback</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportqueueworkitem">StorPortQueueWorkItem</a>.


### -param Worker [in]

A pointer to an opaque buffer that holds context information for the work item returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializeworker">StorPortInitializeWorker</a>.


## -returns



None.




## -remarks



If needed, a work item can be queued within <b>HwStorWorkItem</b>. Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportqueueworkitem">StorPortQueueWorkItem</a> with the current work item to reuse it. Otherwise, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportfreeworker">StorPortFreeWorker</a> to release the work item.

No locks are acquired by Storport when the callback is invoked. The miniport is responsible for any synchronization required in the callback routine.

The name <i>HwStorWorkItem</i> is just a placeholder for the miniport function that is pointed to by the <i>Callback</i> parameter of  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportqueueworkitem">StorPortQueueWorkItem</a>. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
HW_WORKITEM (
    _In_     PVOID HwDeviceExtension,
    _In_Opt_ PVOID Context,
    _In_     PVOID Worker,
    );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportfreeworker">StorPortFreeWorker</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializeworker">StorPortInitializeWorker</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportqueueworkitem">StorPortQueueWorkItem</a>
 

 

