---
UID: NF:storport.StorPortInitializeWorker
title: StorPortInitializeWorker function (storport.h)
description: Creates a new Storport work item that runs in a system worker thread.
old-location: storage\storportinitializeworker.htm
tech.root: storage
ms.assetid: 4472A092-B2F4-4220-9685-6BE4FF0A83DB
ms.date: 03/29/2018
ms.keywords: StorPortInitializeWorker, StorPortInitializeWorker routine [Storage Devices], storage.storportinitializeworker, storport/StorPortInitializeWorker
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortInitializeWorker
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortInitializeWorker function


## -description


Creates a new Storport work item that runs in a system worker thread.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Worker [out]

A pointer to an opaque buffer that holds context information for the work item.


## -returns



The <b>StorPortInitializeWorker</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
Current IRQL > DISPATCH_LEVEL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either <i>HwDeviceExtension</i> or <i>Worker</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
 Insufficient resources are available to initialize the work item context.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The work item was successfully initialized.

</td>
</tr>
</table>
 




## -remarks



The work item context returned in the <i>Worker</i> parameter by <b>StorPortInitializeWorker</b> is used in future calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportqueueworkitem">StorPortQueueWorkItem</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportfreeworker">StorPortFreeWorker</a>.

If the miniport uses the work item during IO processing, we recommended that <b>StorPortInitializeWorker</b> be called during the miniport's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nc-storport-hw_find_adapter">HwStorFindAdapter</a> function to ensure that resources are available when needed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nc-storport-hw_find_adapter">HwStorFindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportfreeworker">StorPortFreeWorker</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportqueueworkitem">StorPortQueueWorkItem</a>
 

 

