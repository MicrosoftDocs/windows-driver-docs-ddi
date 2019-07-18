---
UID: NF:storport.ScsiPortWritePortUlong
title: ScsiPortWritePortUlong macro (storport.h)
description: The ScsiPortWritePortUlong routine transfers a ULONG value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteportulong.htm
tech.root: storage
ms.assetid: 9d2022b7-1e1e-4bc6-b306-84cc249644c5
ms.date: 03/29/2018
ms.keywords: ScsiPortWritePortUlong, ScsiPortWritePortUlong routine [Storage Devices], scsiprt_9a25b2e5-13e4-40f8-8475-dba34ad7ee3c.xml, srb/ScsiPortWritePortUlong, storage.scsiportwriteportulong
ms.topic: macro
f1_keywords:
 - "storport/ScsiPortWritePortUlong"
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
- ScsiPortWritePortUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortWritePortUlong macro


## -description


The <b>ScsiPortWritePortUlong</b> routine transfers a ULONG value to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Value [in]

Specifies the value to be written to the HBA's I/O port.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
 

 

