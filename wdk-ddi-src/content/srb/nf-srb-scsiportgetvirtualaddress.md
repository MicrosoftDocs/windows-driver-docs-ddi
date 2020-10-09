---
UID: NF:srb.ScsiPortGetVirtualAddress
title: ScsiPortGetVirtualAddress function (srb.h)
description: The ScsiPortGetVirtualAddress routine returns a virtual address associated with a physical address if the physical address was obtained by a call to ScsiPortGetPhysicalAddress.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\scsiportgetvirtualaddress.htm
tech.root: storage
ms.assetid: 8e9a247a-f906-4f0e-8249-b67a042aada5
ms.date: 03/29/2018
keywords: ["ScsiPortGetVirtualAddress function"]
ms.keywords: ScsiPortGetVirtualAddress, ScsiPortGetVirtualAddress routine [Storage Devices], scsiprt_4f474eed-75d3-47cd-9473-37d0d15310de.xml, srb/ScsiPortGetVirtualAddress, storage.scsiportgetvirtualaddress
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
 - ScsiPortGetVirtualAddress
 - srb/ScsiPortGetVirtualAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiPortGetVirtualAddress
---

# ScsiPortGetVirtualAddress function


## -description

The <b>ScsiPortGetVirtualAddress</b> routine returns a virtual address associated with a physical address if the physical address was obtained by a call to <b>ScsiPortGetPhysicalAddress</b>.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension->HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportinitialize">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device.

### -param PhysicalAddress 

[in]
Specifies the physical address to be mapped. This value must have been returned by <b>ScsiPortGetPhysicalAddress</b> and must be from an uncached device extension or SRB extension.

## -returns

<b>ScsiPortGetVirtualAddress</b> returns a mapped pointer for the given input address. If the <i>PhysicalAddress</i> value is invalid, it returns <b>NULL</b>.

## -remarks

<b>ScsiPortGetVirtualAddress</b> uses <b>SCSI_PHYSICAL_ADDRESS</b> to represent physical addresses.


```cpp
typedef PHYSICAL_ADDRESS SCSI_PHYSICAL_ADDRESS, *PSCSI_PHYSICAL_ADDRESS;

```

The <b>SCSI_PHYSICAL_ADDRESS</b> type is an operating system-independent data type that SCSI miniport drivers use to represent either a physical addresses or a bus-relative address. 

<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetphysicaladdress">ScsiPortGetPhysicalAddress</a>



<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetuncachedextension">ScsiPortGetUncachedExtension</a>