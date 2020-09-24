---
UID: NF:srb.ScsiPortGetLogicalUnit
title: ScsiPortGetLogicalUnit function (srb.h)
description: The ScsiPortGetLogicalUnit routine returns a pointer to the miniport driver's per-LU storage area for a given peripheral.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportgetlogicalunit.htm
tech.root: storage
ms.assetid: 10088043-fc0b-4df9-a5bf-fdee9740b88a
ms.date: 03/29/2018
keywords: ["ScsiPortGetLogicalUnit function"]
ms.keywords: ScsiPortGetLogicalUnit, ScsiPortGetLogicalUnit routine [Storage Devices], scsiprt_2b4c797a-4fbb-4c0c-913a-628bfb6dab3d.xml, srb/ScsiPortGetLogicalUnit, storage.scsiportgetlogicalunit
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
 - ScsiPortGetLogicalUnit
 - srb/ScsiPortGetLogicalUnit
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiPortGetLogicalUnit
---

# ScsiPortGetLogicalUnit function


## -description

The <b>ScsiPortGetLogicalUnit</b> routine returns a pointer to the miniport driver's per-LU storage area for a given peripheral.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension->HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportinitialize">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device.

### -param PathId 

[in]
Identifies the SCSI bus.

### -param TargetId 

[in]
Identifies the target controller or device on the bus.

### -param Lun 

[in]
Identifies the logical unit number of the target device.

## -returns

<b>ScsiPortGetLogicalUnit</b> returns a pointer to the miniport driver's storage area for the requested logical unit. If the operating system-specific port driver considers this logical unit to be nonexistent, it returns <b>NULL</b>.

## -remarks

<b>ScsiPortGetLogicalUnit</b> is irrelevant if the miniport driver's <b>DriverEntry</b> routine specified zero for the <b>LuExtensionSize</b> in the HW_INITIALIZATION_DATA when it called <b>ScsiPortInitialize</b>. Otherwise, the operating system-specific port driver allocates and initializes with zeros a set of LU extensions of the specified size for the miniport driver to use.

Per-LU storage can be used to store data relevant to a particular peripheral, such as saved data pointers. To access this area, the miniport driver calls <b>ScsiPortGetLogicalUnit</b> when the driver is maintaining information about the state of or current operation for any particular peripheral.

The operating system-specific port driver can consider a logical unit to be nonexistent if there is no active request for that logical unit and the device has never been successfully selected.

## -see-also

<a href="/windows-hardware/drivers/ddi/index">DriverEntry of SCSI Miniport Driver</a>



<a href="/windows-hardware/drivers/ddi/srb/ns-srb-_hw_initialization_data">HW_INITIALIZATION_DATA (SCSI)</a>



<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportinitialize">ScsiPortInitialize</a>



<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportmovememory">ScsiPortMoveMemory</a>