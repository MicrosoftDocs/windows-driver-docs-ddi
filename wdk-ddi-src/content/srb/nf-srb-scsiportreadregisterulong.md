---
UID: NF:srb.ScsiPortReadRegisterUlong
title: ScsiPortReadRegisterUlong function (srb.h)
description: The ScsiPortReadRegisterUlong routine reads a ULONG value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadregisterulong.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ScsiPortReadRegisterUlong function"]
ms.keywords: ScsiPortReadRegisterUlong, ScsiPortReadRegisterUlong routine [Storage Devices], scsiprt_fe99fb31-bbec-4213-bfe5-88efbe2e71e9.xml, srb/ScsiPortReadRegisterUlong, storage.scsiportreadregisterulong
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ScsiPortReadRegisterUlong
 - srb/ScsiPortReadRegisterUlong
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
---

# ScsiPortReadRegisterUlong function


## -description

The <b>ScsiPortReadRegisterUlong</b> routine reads a ULONG value from the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Register [in]


Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.

## -returns

<b>ScsiPortReadRegisterUlong</b> returns a ULONG value from the HBA's register.

## -remarks

<b>ScsiPortReadRegisterUlong</b> ensures that data is transferred correctly.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
