---
UID: NF:srb.ScsiPortWriteRegisterUlong
title: ScsiPortWriteRegisterUlong function
author: windows-driver-content
description: The ScsiPortWriteRegisterUlong routine transfers a ULONG value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteregisterulong.htm
old-project: storage
ms.assetid: d6e05c62-da0c-43a5-b51e-4c73f650b77d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortWriteRegisterUlong, ScsiPortWriteRegisterUlong routine [Storage Devices], scsiprt_8a175f68-d47c-4db0-bc22-bde418a56503.xml, srb/ScsiPortWriteRegisterUlong, storage.scsiportwriteregisterulong
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
-	ScsiPortWriteRegisterUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortWriteRegisterUlong function


## -description


The <b>ScsiPortWriteRegisterUlong</b> routine transfers a ULONG value to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register [in]

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.


### -param Value [in]

Specifies the value to be written to the HBA's register.


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>
 

 

