---
UID: NF:srb.ScsiPortConvertPhysicalAddressToUlong
title: ScsiPortConvertPhysicalAddressToUlong function (srb.h)
description: The ScsiPortConvertPhysicalAddressToUlong routine truncates a SCSI_PHYSICAL_ADDRESS to a ULONG.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportconvertphysicaladdresstoulong.htm
tech.root: storage
ms.assetid: 55c258d2-922a-430a-ba6b-b05a078b712d
ms.date: 03/29/2018
ms.keywords: ScsiPortConvertPhysicalAddressToUlong, ScsiPortConvertPhysicalAddressToUlong routine [Storage Devices], scsiprt_5417817d-81ab-4ba9-96f6-589991aecfce.xml, srb/ScsiPortConvertPhysicalAddressToUlong, storage.scsiportconvertphysicaladdresstoulong
f1_keywords:
 - "srb/ScsiPortConvertPhysicalAddressToUlong"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Scsiport.lib
- Scsiport.dll
api_name:
- ScsiPortConvertPhysicalAddressToUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortConvertPhysicalAddressToUlong function


## -description


The <b>ScsiPortConvertPhysicalAddressToUlong</b> routine truncates a SCSI_PHYSICAL_ADDRESS to a ULONG.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Address [in]

Specifies a value of type SCSI_PHYSICAL_ADDRESS.


## -returns



<b>ScsiPortConvertPhysicalAddressToUlong</b> returns the low-order part of the given SCSI_PHYSICAL_ADDRESS value. A miniport driver cannot call this routine to truncate a 64-bit physical address. Such addresses should be used as quadword values, which contain all 64 bits.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_access_range">ACCESS_RANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetphysicaladdress">ScsiPortGetPhysicalAddress</a>
 

 

