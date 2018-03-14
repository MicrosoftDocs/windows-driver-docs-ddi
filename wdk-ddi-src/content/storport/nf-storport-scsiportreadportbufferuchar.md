---
UID: NF:storport.ScsiPortReadPortBufferUchar
title: ScsiPortReadPortBufferUchar macro
author: windows-driver-content
description: The ScsiPortReadPortBufferUchar routine transfers a given number of unsigned byte values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadportbufferuchar.htm
old-project: storage
ms.assetid: 9444670d-5b9f-4d77-b867-ac5608c24e02
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ScsiPortReadPortBufferUchar, ScsiPortReadPortBufferUchar routine [Storage Devices], scsiprt_db25989e-3b44-4f45-b768-b1b11c2ed25a.xml, srb/ScsiPortReadPortBufferUchar, storage.scsiportreadportbufferuchar
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
-	ScsiPortReadPortBufferUchar
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# ScsiPortReadPortBufferUchar macro


## -description


The <b>ScsiPortReadPortBufferUchar</b> routine transfers a given number of unsigned byte values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID ScsiPortReadPortBufferUchar(
  _In_ PUCHAR Port,
  _In_ PUCHAR Buffer,
  _In_ ULONG  Count
);
````


## -parameters




### -param Port [in]

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Buffer [in]

Pointer to the buffer.


### -param Count [in]

Specifies the number of bytes to be read from the HBA.


## -remarks



<b>ScsiPortReadPortBufferUchar</b> ensures that the data is transferred correctly.




## -see-also

<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>



 

 


