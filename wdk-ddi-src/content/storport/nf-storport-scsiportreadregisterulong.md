---
UID: NF:storport.ScsiPortReadRegisterUlong
title: ScsiPortReadRegisterUlong macro (storport.h)
description: The ScsiPortReadRegisterUlong routine reads a ULONG value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadregisterulong.htm
tech.root: storage
ms.assetid: e644fce4-2367-4851-8252-47a25faf0b6d
ms.date: 03/29/2018
keywords: ["ScsiPortReadRegisterUlong macro"]
ms.keywords: ScsiPortReadRegisterUlong, ScsiPortReadRegisterUlong routine [Storage Devices], scsiprt_fe99fb31-bbec-4213-bfe5-88efbe2e71e9.xml, srb/ScsiPortReadRegisterUlong, storage.scsiportreadregisterulong
f1_keywords:
 - "storport/ScsiPortReadRegisterUlong"
 - "ScsiPortReadRegisterUlong"
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
- ScsiPortReadRegisterUlong
targetos: Windows
req.typenames: 
---

# ScsiPortReadRegisterUlong macro


## -description


The <b>ScsiPortReadRegisterUlong</b> routine reads a ULONG value from the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register 
[in]
Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.


## -remarks



<b>ScsiPortReadRegisterUlong</b> ensures that data is transferred correctly.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
 

 

