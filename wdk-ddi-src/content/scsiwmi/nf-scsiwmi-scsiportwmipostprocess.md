---
UID: NF:scsiwmi.ScsiPortWmiPostProcess
title: ScsiPortWmiPostProcess function
author: windows-driver-content
description: The ScsiPortWmiPostProcess routine updates a request context for a WMI SRB.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwmipostprocess.htm
old-project: storage
ms.assetid: da1770bc-2233-47ef-afab-cfcb34edb4b9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortWmiPostProcess, ScsiPortWmiPostProcess routine [Storage Devices], scsiprt_e10d02e1-18d2-4152-ac11-83bdcbb2ce49.xml, scsiwmi/ScsiPortWmiPostProcess, storage.scsiportwmipostprocess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: scsiwmi.h
req.include-header: Miniport.h, Scsi.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	scsiwmi.h
api_name:
-	ScsiPortWmiPostProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortWmiPostProcess function


## -description


The <b>ScsiPortWmiPostProcess</b> routine updates a request context for a WMI SRB.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param RequestContext [in]

A pointer to the request context for this SRB.


### -param SrbStatus [in]

Specifies any valid SRB status. If the output buffer passed to the miniport driver was too small to contain all of the data from a request, the miniport driver sets <i>SrbStatus</i> to SRB_STATUS_DATA_OVERRUN.


### -param BufferUsed [in]

If <i>SrbStatus</i> indicates success, the miniport driver sets <i>BufferUsed</i> to the number of bytes of data written to the buffer. If <i>SrbStatus</i> is SRB_STATUS_DATA_OVERRUN, the miniport driver sets <i>BufferUsed</i> to the number of bytes required to complete the SRB successfully.


## -returns



None




## -remarks



A miniport driver must call <b>ScsiPortWmiPostProcess</b> after the WMI SRB request has been processed and is ready to be completed.

For synchronous SRBs, <b>ScsiPortWmiPostProcess</b> is called in the callback routine.

For pending SRBs, <b>ScsiPortWmiPostProcess</b> is called after the SRB has been processed, and before it is completed.

If a miniport driver sets <i>SrbStatus</i> to SRB_STATUS_DATA_OVERRUN and sets <i>BufferUsed</i>, successive identical WMI SRBs with an allocated buffer equal to or greater than <i>BufferUsed</i> bytes should succeed. This should be achieved if the driver sets the exact value for <i>BufferUsed</i> that is needed to complete the request when calling <b>ScsiPortWmiPostProcess</b> with <i>SrbStatus</i> equal to SRB_STATUS_DATA_OVERRUN. For a variable-sized output structure, the input data buffer of the SRB should have enough information to determine the exact <i>BufferUsed</i> value. If the input data buffer does not contain enough information, the driver should never fail the same SRB two times with SRB_STATUS_DATA_OVERRUN. Instead, the driver should set SRB_STATUS_DATA_OVERRUN and request the minimum size necessary for the output buffer first, and then set SRB_STATUS_SUCCESS and indicate the failure in the contents of the output buffer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564946">SCSIWMI_REQUEST_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564789">ScsiPortWmiGetReturnSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564791">ScsiPortWmiGetReturnStatus</a>
 

 

