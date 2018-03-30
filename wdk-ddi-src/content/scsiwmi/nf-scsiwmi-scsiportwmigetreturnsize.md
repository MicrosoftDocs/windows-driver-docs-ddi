---
UID: NF:scsiwmi.ScsiPortWmiGetReturnSize
title: ScsiPortWmiGetReturnSize macro
author: windows-driver-content
description: The ScsiPortWmiGetReturnSize routine indicates the number of bytes of data to be returned by a miniport driver for a WMI SRB.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwmigetreturnsize.htm
old-project: storage
ms.assetid: 7cd54ac2-e13b-45eb-a0ac-56a2d60d9057
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ScsiPortWmiGetReturnSize, ScsiPortWmiGetReturnSize macro [Storage Devices], scsiprt_a9717bc6-2519-4446-8965-47340976a85f.xml, scsiwmi/ScsiPortWmiGetReturnSize, storage.scsiportwmigetreturnsize
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	ScsiPortWmiGetReturnSize
product: Windows
targetos: Windows
req.typenames: SCSIWMI_ENABLE_DISABLE_CONTROL
req.product: Windows 10 or later.
---

# ScsiPortWmiGetReturnSize macro


## -description


The <b>ScsiPortWmiGetReturnSize</b> routine indicates the number of bytes of data to be returned by a miniport driver for a WMI SRB.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param RequestContext

Pointer to the request context for this SRB.


## -remarks



A miniport driver must call <b>ScsiPortWmiGetReturnSize</b> to obtain the value to put into <b>Srb-&gt;DataTransferLength</b> before completing the SRB. <b>ScsiPortWmiGetReturnSize</b> should be called sometime after the miniport driver calls <b>ScsiWmiPostProcess</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564946">SCSIWMI_REQUEST_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564791">ScsiPortWmiGetReturnStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564796">ScsiPortWmiPostProcess</a>
 

 

