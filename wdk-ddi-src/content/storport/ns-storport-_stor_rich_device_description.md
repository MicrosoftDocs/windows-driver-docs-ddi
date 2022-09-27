---
UID: NS:storport._STOR_RICH_DEVICE_DESCRIPTION
title: STOR_RICH_DEVICE_DESCRIPTION (storport.h)
description: The STOR_RICH_DEVICE_DESCRIPTION structure describes the attributes of the physical device for which a driver is requesting a DMA (direct memory access) adapter.
old-location: storage\stor_rich_device_description.htm
tech.root: storage
ms.date: 08/26/2022
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

# STOR_RICH_DEVICE_DESCRIPTION structure

## -description

The **STOR_RICH_DEVICE_DESCRIPTION** structure describes the attributes of the **physical device** for which a driver is requesting a DMA (direct memory access) adapter.

## -struct-fields

### -field Version

The version of the structure. Must be **STOR_RICH_DEVICE_DESCRIPTION_STRUCTURE_VERSION**.

### -field Size

The size of the structure, in bytes.

### -field VendorId[STOR_VENDOR_ID_LENGTH + 1]

A string representing the device’s vendor ID. May be an empty string if **ModelNumber** is provided.

### -field ModelNumber[STOR_MODEL_NUMBER_LENGTH + 1]

A string representing the device’s model.

### -field FirmwareRevision[STOR_FIRMWARE_REVISION_LENGTH + 1]

A string representing the device’s currently active firmware revision.

## -remarks

A miniport can choose to support this unit control if the device reports longer **ModelNumber** or **FirmwareRevision** information than defined in SCSI.

This is invoked during the unit enumeration process or the device description update process. **ScsiUnitRichDescription** is a caller-allocated version of this structure.

## -see-also

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)
