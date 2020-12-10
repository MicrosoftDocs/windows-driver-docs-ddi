---
UID: NF:storport.ScsiPortWritePortUshort
title: ScsiPortWritePortUshort macro (storport.h)
description: The ScsiPortWritePortUshort routine transfers a USHORT value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteportushort.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ScsiPortWritePortUshort macro"]
ms.keywords: ScsiPortWritePortUshort, ScsiPortWritePortUshort routine [Storage Devices], scsiprt_e7e27190-3f51-4ede-9b4d-fcc437f46d17.xml, srb/ScsiPortWritePortUshort, storage.scsiportwriteportushort
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ScsiPortWritePortUshort
 - storport/ScsiPortWritePortUshort
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
---

# ScsiPortWritePortUshort macro


## -description

The <b>ScsiPortWritePortUshort</b> routine transfers a USHORT value to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Port 

[in]
Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.

### -param Value 

[in]
Specifies the value to be written to the HBA's I/O port.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
