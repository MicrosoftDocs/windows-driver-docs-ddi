---
UID: NS:storport._STOR_RICH_DEVICE_DESCRIPTION
title: _STOR_RICH_DEVICE_DESCRIPTION (storport.h)
description: The STOR_RICH_DEVICE_DESCRIPTION structure describes the attributes of the physical device for which a driver is requesting a DMA (direct memory access) adapter.
old-location: storage\stor_rich_device_description.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["STOR_RICH_DEVICE_DESCRIPTION structure"]
ms.keywords: "*PSTOR_RICH_DEVICE_DESCRIPTION, PSTOR_RICH_DEVICE_DESCRIPTION, PSTOR_RICH_DEVICE_DESCRIPTION structure pointer [Storage Devices], STOR_RICH_DEVICE_DESCRIPTION, STOR_RICH_DEVICE_DESCRIPTION structure [Storage Devices], _STOR_RICH_DEVICE_DESCRIPTION, storage.stor_rich_device_description, storport/PSTOR_RICH_DEVICE_DESCRIPTION, storport/STOR_RICH_DEVICE_DESCRIPTION"
req.header: storport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: STOR_RICH_DEVICE_DESCRIPTION, *PSTOR_RICH_DEVICE_DESCRIPTION
f1_keywords:
 - _STOR_RICH_DEVICE_DESCRIPTION
 - storport/_STOR_RICH_DEVICE_DESCRIPTION
 - PSTOR_RICH_DEVICE_DESCRIPTION
 - storport/PSTOR_RICH_DEVICE_DESCRIPTION
 - STOR_RICH_DEVICE_DESCRIPTION
 - storport/STOR_RICH_DEVICE_DESCRIPTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Storport.h
api_name:
 - _STOR_RICH_DEVICE_DESCRIPTION
 - PSTOR_RICH_DEVICE_DESCRIPTION
 - STOR_RICH_DEVICE_DESCRIPTION
---

# _STOR_RICH_DEVICE_DESCRIPTION structure


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>STOR_RICH_DEVICE_DESCRIPTION</b> structure describes the attributes of the <b> physical device </b> for which a driver is requesting a DMA (direct memory access) adapter.

## -struct-fields

### -field Version

The version of the structure. Must be STOR_RICH_DEVICE_DESCRIPTION_STRUCTURE_VERSION.

### -field Size

The size of the structure.

### -field VendorId

A string representing the device’s vendor ID. May be an empty string if ModelNumber is provided.

### -field ModelNumber

A string representing the device’s model.

### -field FirmwareRevision

A string representing the device’s currently active firmware revision.

## -remarks

Miniport can choose to support this UnitControl if the device reports longer Model or Firmware information than defined in SCSI.

This is invoked during the Unit enumeration process or the device description update process. ScsiUnitRichDescription is a caller-allocated version of this structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_unit_control">HwStorUnitControl</a>

