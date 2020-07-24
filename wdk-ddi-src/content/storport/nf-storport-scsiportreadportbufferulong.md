---
UID: NF:storport.ScsiPortReadPortBufferUlong
title: ScsiPortReadPortBufferUlong macro (storport.h)
description: The ScsiPortReadPortBufferUlong routine transfers a given number of ULONG values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadportbufferulong.htm
tech.root: storage
ms.assetid: 719210f5-22d6-425d-aff0-aefbebfbfca2
ms.date: 03/29/2018
keywords: ["ScsiPortReadPortBufferUlong macro"]
ms.keywords: ScsiPortReadPortBufferUlong, ScsiPortReadPortBufferUlong routine [Storage Devices], scsiprt_5da99f27-5758-4e1b-af45-0d9069b55af7.xml, srb/ScsiPortReadPortBufferUlong, storage.scsiportreadportbufferulong
f1_keywords:
 - "storport/ScsiPortReadPortBufferUlong"
 - "ScsiPortReadPortBufferUlong"
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
- ScsiPortReadPortBufferUlong
targetos: Windows
req.typenames: 
---

# ScsiPortReadPortBufferUlong macro


## -description


The <b>ScsiPortReadPortBufferUlong</b> routine transfers a given number of ULONG values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Buffer [in]

Pointer to the buffer.


### -param Count [in]

Specifies the number of ULONG values to read from the HBA.


## -remarks



<b>ScsiPortReadPortBufferUlong</b> ensures that the data is transferred correctly.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
 

 

