---
UID: NF:storport.ScsiPortReadPortBufferUshort
title: ScsiPortReadPortBufferUshort macro
author: windows-driver-content
description: The ScsiPortReadPortBufferUshort routine transfers a given number of USHORT values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadportbufferushort.htm
tech.root: storage
ms.assetid: b218785c-170e-4a30-99c9-0db8705b7f5d
ms.date: 3/29/2018
ms.keywords: ScsiPortReadPortBufferUshort, ScsiPortReadPortBufferUshort routine [Storage Devices], scsiprt_27acea07-f416-4fa1-894d-6bb38c020f6b.xml, srb/ScsiPortReadPortBufferUshort, storage.scsiportreadportbufferushort
ms.topic: macro
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Scsiport.lib
-	Scsiport.dll
api_name:
-	ScsiPortReadPortBufferUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortReadPortBufferUshort macro


## -description


The <b>ScsiPortReadPortBufferUshort</b> routine transfers a given number of USHORT values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Buffer [in]

Pointer to the buffer.


### -param Count [in]

Specifies the number of USHORT values to read from the HBA.


## -remarks



<b>ScsiPortReadPortBufferUshort</b> ensures that the data is transferred correctly.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>
 

 

