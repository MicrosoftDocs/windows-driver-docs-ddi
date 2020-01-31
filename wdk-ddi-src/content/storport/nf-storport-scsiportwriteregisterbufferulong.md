---
UID: NF:storport.ScsiPortWriteRegisterBufferUlong
title: ScsiPortWriteRegisterBufferUlong macro (storport.h)
description: The ScsiPortWriteRegisterBufferUlong routine transfers a given number of ULONG values from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteregisterbufferulong.htm
tech.root: storage
ms.assetid: d77b188e-45b2-47c3-bee5-557886925d3f
ms.date: 03/29/2018
ms.keywords: ScsiPortWriteRegisterBufferUlong, ScsiPortWriteRegisterBufferUlong routine [Storage Devices], scsiprt_f6ce8fd2-0d06-4bda-9673-983af38f08e9.xml, srb/ScsiPortWriteRegisterBufferUlong, storage.scsiportwriteregisterbufferulong
f1_keywords:
 - "storport/ScsiPortWriteRegisterBufferUlong"
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
- ScsiPortWriteRegisterBufferUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortWriteRegisterBufferUlong macro


## -description


The <b>ScsiPortWriteRegisterBufferUlong</b> routine transfers a given number of ULONG values from a buffer to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register [in]

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Buffer [in]

Pointer to a buffer containing the data to be written.


### -param Count [in]

Specifies the number of ULONG values to be transferred to the HBA.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
 

 

