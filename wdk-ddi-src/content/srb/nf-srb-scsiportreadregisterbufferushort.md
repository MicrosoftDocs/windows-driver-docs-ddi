---
UID: NF:srb.ScsiPortReadRegisterBufferUshort
title: ScsiPortReadRegisterBufferUshort function (srb.h)
description: The ScsiPortReadRegisterBufferUshort routine transfers a specified number of USHORT values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadregisterbufferushort.htm
tech.root: storage
ms.assetid: 6db90186-a663-4710-8209-abd5ef2b361a
ms.date: 03/29/2018
ms.keywords: ScsiPortReadRegisterBufferUshort, ScsiPortReadRegisterBufferUshort routine [Storage Devices], scsiprt_f6e36a20-066b-4b3e-bf94-9182e84dc2eb.xml, srb/ScsiPortReadRegisterBufferUshort, storage.scsiportreadregisterbufferushort
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
- ScsiPortReadRegisterBufferUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortReadRegisterBufferUshort function


## -description


The <b>ScsiPortReadRegisterBufferUshort</b> routine transfers a specified number of USHORT values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register [in]

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Buffer [in]

Pointer to the buffer.


### -param Count [in]

Specifies the number of USHORT values to be read from the HBA.


## -returns



None




## -remarks



<b>ScsiPortReadRegisterBufferUshort</b> ensures that the data has been transferred correctly.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
 

 

