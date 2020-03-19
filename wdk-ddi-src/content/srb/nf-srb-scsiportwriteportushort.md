---
UID: NF:srb.ScsiPortWritePortUshort
title: ScsiPortWritePortUshort function (srb.h)
description: The ScsiPortWritePortUshort routine transfers a USHORT value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteportushort.htm
tech.root: storage
ms.assetid: 4b1accd8-5dbe-47d6-822e-1997a6ab5082
ms.date: 03/29/2018
keywords: ["ScsiPortWritePortUshort function"]
ms.keywords: ScsiPortWritePortUshort, ScsiPortWritePortUshort routine [Storage Devices], scsiprt_e7e27190-3f51-4ede-9b4d-fcc437f46d17.xml, srb/ScsiPortWritePortUshort, storage.scsiportwriteportushort
f1_keywords:
 - "srb/ScsiPortWritePortUshort"
req.header: srb.h
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
- ScsiPortWritePortUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortWritePortUshort function


## -description


The <b>ScsiPortWritePortUshort</b> routine transfers a USHORT value to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Value [in]

Specifies the value to be written to the HBA's I/O port.


## -returns



None




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
 

 

