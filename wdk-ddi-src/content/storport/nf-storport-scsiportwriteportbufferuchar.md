---
UID: NF:storport.ScsiPortWritePortBufferUchar
title: ScsiPortWritePortBufferUchar macro
author: windows-driver-content
description: The ScsiPortWritePortBufferUchar routine transfers a given number of unsigned bytes from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteportbufferuchar.htm
tech.root: storage
ms.assetid: 83b6425f-52fa-4c57-aac5-698d3a586248
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortWritePortBufferUchar, ScsiPortWritePortBufferUchar routine [Storage Devices], scsiprt_19277863-04fb-4f72-85f5-9bc877bd83c1.xml, srb/ScsiPortWritePortBufferUchar, storage.scsiportwriteportbufferuchar
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	ScsiPortWritePortBufferUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortWritePortBufferUchar macro


## -description


The <b>ScsiPortWritePortBufferUchar</b> routine transfers a given number of unsigned bytes from a buffer to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Buffer [in]

Pointer to a buffer.


### -param Count [in]

Specifies the number of bytes to be written to the HBA.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>
 

 

