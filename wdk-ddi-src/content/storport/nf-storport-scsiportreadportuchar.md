---
UID: NF:storport.ScsiPortReadPortUchar
title: ScsiPortReadPortUchar macro (storport.h)
description: The ScsiPortReadPortUchar routine reads an unsigned byte value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadportuchar.htm
tech.root: storage
ms.assetid: aaf7e821-4f60-4018-b0ee-d0f3995482c4
ms.date: 03/29/2018
keywords: ["ScsiPortReadPortUchar macro"]
ms.keywords: ScsiPortReadPortUchar, ScsiPortReadPortUchar routine [Storage Devices], scsiprt_bdc335c6-bee2-47f6-ad8e-61bece6f7c15.xml, srb/ScsiPortReadPortUchar, storage.scsiportreadportuchar
f1_keywords:
 - "storport/ScsiPortReadPortUchar"
 - "ScsiPortReadPortUchar"
req.header: storport.h
req.include-header: Miniport.h, Scsi.h, Storport.h
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Scsiport.lib
- Scsiport.dll
api_name:
- ScsiPortReadPortUchar
targetos: Windows
req.typenames: 
---

# ScsiPortReadPortUchar macro


## -description


The <b>ScsiPortReadPortUchar</b> routine reads an unsigned byte value from the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.


## -remarks



<b>ScsiPortReadPortUchar</b> ensures that the data is transferred correctly.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
 

 

