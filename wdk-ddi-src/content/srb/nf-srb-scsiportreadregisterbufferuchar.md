---
UID: NF:srb.ScsiPortReadRegisterBufferUchar
title: ScsiPortReadRegisterBufferUchar function (srb.h)
description: The ScsiPortReadRegisterBufferUchar routine transfers a specified number of unsigned bytes from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadregisterbufferuchar.htm
tech.root: storage
ms.assetid: 5574d8ee-8a52-488f-849d-9288af5fed2b
ms.date: 03/29/2018
ms.keywords: ScsiPortReadRegisterBufferUchar, ScsiPortReadRegisterBufferUchar routine [Storage Devices], scsiprt_cfe4caf7-bfae-4d7a-aa70-8f44b52ca33c.xml, srb/ScsiPortReadRegisterBufferUchar, storage.scsiportreadregisterbufferuchar
ms.topic: function
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
- ScsiPortReadRegisterBufferUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortReadRegisterBufferUchar function


## -description


The <b>ScsiPortReadRegisterBufferUchar</b> routine transfers a specified number of unsigned bytes from the HBA to a buffer.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register [in]

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Buffer [in]

Pointer to the buffer.


### -param Count [in]

Specifies the number of bytes to be read from the HBA.


## -returns



None




## -remarks



<b>ScsiPortReadRegisterBufferUchar</b> ensures that the data is transferred correctly.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
 

 

