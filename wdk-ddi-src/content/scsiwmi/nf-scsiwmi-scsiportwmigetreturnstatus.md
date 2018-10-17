---
UID: NF:scsiwmi.ScsiPortWmiGetReturnStatus
title: ScsiPortWmiGetReturnStatus macro
author: windows-driver-content
description: The ScsiPortWmiGetReturnStatus routine returns the status of a WMI SRB.
old-location: storage\scsiportwmigetreturnstatus.htm
tech.root: storage
ms.assetid: 79213f47-ba4c-41b0-b095-1b5c25c79456
ms.date: 3/29/2018
ms.keywords: ScsiPortWmiGetReturnStatus, ScsiPortWmiGetReturnStatus macro [Storage Devices], scsiprt_cb3693a3-2fab-4d25-9c64-84327a7ef61c.xml, scsiwmi/ScsiPortWmiGetReturnStatus, storage.scsiportwmigetreturnstatus
ms.topic: macro
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
-	ScsiPortWmiGetReturnStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortWmiGetReturnStatus macro


## -description


The <b>ScsiPortWmiGetReturnStatus</b> routine returns the status of a WMI SRB. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param RequestContext

Pointer to the request context for this SRB.


## -remarks



A miniport driver must call <b>ScsiPortWmiGetReturnStatus</b> to obtain the value to put into <b>Srb-&gt;SrbStatus</b>. <b>ScsiPortWmiGetReturnStatus</b> should be called sometime after the miniport driver calls <b>ScsiPortWmiPostProcess.</b>




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564946">SCSIWMI_REQUEST_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564791">ScsiPortWmiGetReturnStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564796">ScsiPortWmiPostProcess</a>
 

 

