---
UID: NF:srb.ScsiPortConvertUlongToPhysicalAddress
title: ScsiPortConvertUlongToPhysicalAddress function (srb.h)
description: The ScsiPortConvertUlongToPhysicalAddress routine extends a given ULONG address into a value of type SCSI_PHYSICAL_ADDRESS.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportconvertulongtophysicaladdress.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ScsiPortConvertUlongToPhysicalAddress function"]
ms.keywords: ScsiPortConvertUlongToPhysicalAddress, ScsiPortConvertUlongToPhysicalAddress routine [Storage Devices], scsiprt_9dc27865-55c2-4599-913c-babe77c62af9.xml, srb/ScsiPortConvertUlongToPhysicalAddress, storage.scsiportconvertulongtophysicaladdress
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ScsiPortConvertUlongToPhysicalAddress
 - srb/ScsiPortConvertUlongToPhysicalAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiPortConvertUlongToPhysicalAddress
---

# ScsiPortConvertUlongToPhysicalAddress function


## -description

The <b>ScsiPortConvertUlongToPhysicalAddress</b> routine extends a given ULONG address into a value of type SCSI_PHYSICAL_ADDRESS.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param UlongAddress 

[in]
Specifies a value of type ULONG.

## -returns

<b>ScsiPortConvertUlongToPhysicalAddress</b> returns the converted SCSI_PHYSICAL_ADDRESS.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/ns-srb-_access_range">ACCESS_RANGE</a>



<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>



<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetvirtualaddress">ScsiPortGetVirtualAddress</a>
