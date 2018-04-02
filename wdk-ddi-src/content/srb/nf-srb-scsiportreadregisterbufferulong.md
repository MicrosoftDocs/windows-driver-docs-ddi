---
UID: NF:srb.ScsiPortReadRegisterBufferUlong
title: ScsiPortReadRegisterBufferUlong function
author: windows-driver-content
description: The ScsiPortReadRegisterBufferUlong routine transfers a specified number of ULONG values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadregisterbufferulong.htm
old-project: storage
ms.assetid: 6b2d1893-8878-4ccd-bc0c-845e1cb8f6bf
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortReadRegisterBufferUlong, ScsiPortReadRegisterBufferUlong routine [Storage Devices], scsiprt_4356902d-5810-4006-acbe-40d41c2d68e4.xml, srb/ScsiPortReadRegisterBufferUlong, storage.scsiportreadregisterbufferulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Scsiport.lib
-	Scsiport.dll
api_name:
-	ScsiPortReadRegisterBufferUlong
product: Windows
targetos: Windows
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
req.product: Windows 10 or later.
---

# ScsiPortReadRegisterBufferUlong function


## -description


The <b>ScsiPortReadRegisterBufferUlong</b> routine transfers a specified number of ULONG values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register [in]

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Buffer [in]

Pointer to the buffer.


### -param Count [in]

Specifies the number of ULONG values to be read from the HBA.


## -returns



None




## -remarks



<b>ScsiPortReadRegisterBufferUlong</b> ensures that the data is transferred correctly.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>
 

 

