---
UID: NF:storport.ScsiPortReadPortUshort
title: ScsiPortReadPortUshort macro (storport.h)
description: The ScsiPortReadPortUshort routine reads a USHORT value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadportushort.htm
tech.root: storage
ms.assetid: eb21d8ef-4ad5-48b3-8619-3ed5040652b0
ms.date: 03/29/2018
ms.keywords: ScsiPortReadPortUshort, ScsiPortReadPortUshort routine [Storage Devices], scsiprt_3b90fdff-db04-43ca-9c62-8552eed87feb.xml, srb/ScsiPortReadPortUshort, storage.scsiportreadportushort
ms.topic: macro
f1_keywords:
 - "storport/ScsiPortReadPortUshort"
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
- ScsiPortReadPortUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortReadPortUshort macro


## -description


The <b>ScsiPortReadPortUshort</b> routine reads a USHORT value from the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.


## -remarks



<b>ScsiPortReadPortUshort</b> ensures that the data is transferred correctly.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
 

 

