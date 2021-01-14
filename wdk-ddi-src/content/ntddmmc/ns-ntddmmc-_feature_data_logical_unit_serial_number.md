---
UID: NS:ntddmmc._FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
title: _FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER (ntddmmc.h)
description: The FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure holds information about the Device Serial Number feature.
old-location: storage\feature_data_logical_unit_serial_number.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure"]
ms.keywords: "*PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure [Storage Devices], PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure pointer [Storage Devices], _FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, ntddmmc/FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, ntddmmc/PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, storage.feature_data_logical_unit_serial_number, structs-CD-ROM_c7f48548-00ff-49a8-93ac-2cab0e838e14.xml"
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER, *PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
f1_keywords:
 - _FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
 - ntddmmc/_FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
 - PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
 - ntddmmc/PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
 - FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
 - ntddmmc/FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - _FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
 - PFEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
 - FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER
---

# _FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure


## -description

The FEATURE_DATA_LOGICAL_UNIT_SERIAL_NUMBER structure holds information about the Device Serial Number feature.

## -struct-fields

### -field Header

Contains a <a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor.

### -field SerialNumber

Contains an array that indicates the serial number of the device in ASCII graphic codes (0x020 through 0x07e).

## -remarks

This structure holds data for the feature named "Device Serial Number" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can furnish the initiator with a serial number that uniquely identifies the device.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>

