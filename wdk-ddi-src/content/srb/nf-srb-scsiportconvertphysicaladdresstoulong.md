---
UID: NF:srb.ScsiPortConvertPhysicalAddressToUlong
title: ScsiPortConvertPhysicalAddressToUlong function
author: windows-driver-content
description: The ScsiPortConvertPhysicalAddressToUlong routine truncates a SCSI_PHYSICAL_ADDRESS to a ULONG.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportconvertphysicaladdresstoulong.htm
old-project: storage
ms.assetid: 55c258d2-922a-430a-ba6b-b05a078b712d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ScsiPortConvertPhysicalAddressToUlong, ScsiPortConvertPhysicalAddressToUlong routine [Storage Devices], scsiprt_5417817d-81ab-4ba9-96f6-589991aecfce.xml, srb/ScsiPortConvertPhysicalAddressToUlong, storage.scsiportconvertphysicaladdresstoulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
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
-	ScsiPortConvertPhysicalAddressToUlong
product: Windows
targetos: Windows
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
req.product: Windows 10 or later.
---

# ScsiPortConvertPhysicalAddressToUlong function


## -description


The <b>ScsiPortConvertPhysicalAddressToUlong</b> routine truncates a SCSI_PHYSICAL_ADDRESS to a ULONG.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Address [in]

Specifies a value of type SCSI_PHYSICAL_ADDRESS.


## -returns



<b>ScsiPortConvertPhysicalAddressToUlong</b> returns the low-order part of the given SCSI_PHYSICAL_ADDRESS value. A miniport driver cannot call this routine to truncate a 64-bit physical address. Such addresses should be used as quadword values, which contain all 64 bits.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550117">ACCESS_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564636">ScsiPortGetPhysicalAddress</a>
 

 

