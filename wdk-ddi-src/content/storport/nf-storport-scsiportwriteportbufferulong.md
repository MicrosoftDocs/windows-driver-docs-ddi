---
UID: NF:storport.ScsiPortWritePortBufferUlong
title: ScsiPortWritePortBufferUlong macro (storport.h)
description: The ScsiPortWritePortBufferUlong routine transfers a given number of ULONG values from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteportbufferulong.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ScsiPortWritePortBufferUlong macro"]
ms.keywords: ScsiPortWritePortBufferUlong, ScsiPortWritePortBufferUlong routine [Storage Devices], scsiprt_314b08e6-e579-4faa-b009-e12ad8f946bc.xml, srb/ScsiPortWritePortBufferUlong, storage.scsiportwriteportbufferulong
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
 - ScsiPortWritePortBufferUlong
 - storport/ScsiPortWritePortBufferUlong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiPortWritePortBufferUlong
---

# ScsiPortWritePortBufferUlong macro


## -description

The <b>ScsiPortWritePortBufferUlong</b> routine transfers a given number of ULONG values from a buffer to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Port 

[in]
Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.

### -param Buffer 

[in]
Pointer to the buffer.

### -param Count 

[in]
Specifies the number of ULONG values to be written to the HBA.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
