---
UID: NF:srb.ScsiPortReadRegisterUchar
title: ScsiPortReadRegisterUchar function (srb.h)
description: The ScsiPortReadRegisterUchar routine reads an unsigned byte value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadregisteruchar.htm
tech.root: storage
ms.assetid: d5ea19e5-015d-451e-8e28-0b5a226f291a
ms.date: 03/29/2018
ms.keywords: ScsiPortReadRegisterUchar, ScsiPortReadRegisterUchar routine [Storage Devices], scsiprt_220f8972-dc09-4027-9cec-85a07ed5547d.xml, srb/ScsiPortReadRegisterUchar, storage.scsiportreadregisteruchar
f1_keywords:
 - "srb/ScsiPortReadRegisterUchar"
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
- ScsiPortReadRegisterUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortReadRegisterUchar function


## -description


The <b>ScsiPortReadRegisterUchar</b> routine reads an unsigned byte value from the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register [in]

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.


## -returns



<b>ScsiPortReadRegisterUchar</b> returns an unsigned byte from the HBA's register.




## -remarks



<b>ScsiPortReadRegisterUchar</b> ensures that the data is transferred correctly.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
 

 

