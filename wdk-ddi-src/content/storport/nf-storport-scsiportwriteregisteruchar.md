---
UID: NF:storport.ScsiPortWriteRegisterUchar
title: ScsiPortWriteRegisterUchar macro (storport.h)
description: The ScsiPortWriteRegisterUchar routine transfers a unsigned byte value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteregisteruchar.htm
tech.root: storage
ms.assetid: 67764b34-3bd3-42ad-a1f8-765b4f11fcf6
ms.date: 03/29/2018
keywords: ["ScsiPortWriteRegisterUchar macro"]
ms.keywords: ScsiPortWriteRegisterUchar, ScsiPortWriteRegisterUchar routine [Storage Devices], scsiprt_11b9d3b9-2866-4f07-a685-68d48e993748.xml, srb/ScsiPortWriteRegisterUchar, storage.scsiportwriteregisteruchar
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
 - ScsiPortWriteRegisterUchar
 - storport/ScsiPortWriteRegisterUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiPortWriteRegisterUchar
---

# ScsiPortWriteRegisterUchar macro


## -description

The <b>ScsiPortWriteRegisterUchar</b> routine transfers a unsigned byte value to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Register 

[in]
Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.

### -param Value 

[in]
Specifies the value to be written to the HBA's register.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>

