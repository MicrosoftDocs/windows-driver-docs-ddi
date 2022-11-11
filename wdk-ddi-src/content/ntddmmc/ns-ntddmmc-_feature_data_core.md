---
UID: NS:ntddmmc._FEATURE_DATA_CORE
title: FEATURE_DATA_CORE (ntddmmc.h)
description: The FEATURE_DATA_CORE structure holds data for the Core feature descriptor.
old-location: storage\feature_data_core.htm
tech.root: storage
ms.date: 11/10/2022
keywords: ["FEATURE_DATA_CORE structure"]
ms.keywords: "*PFEATURE_DATA_CORE, FEATURE_DATA_CORE, FEATURE_DATA_CORE structure [Storage Devices], PFEATURE_DATA_CORE, PFEATURE_DATA_CORE structure pointer [Storage Devices], _FEATURE_DATA_CORE, ntddmmc/FEATURE_DATA_CORE, ntddmmc/PFEATURE_DATA_CORE, storage.feature_data_core, structs-CD-ROM_1b2608f2-398d-4733-b319-a92d932504e7.xml"
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
req.typenames: FEATURE_DATA_CORE, *PFEATURE_DATA_CORE
f1_keywords:
 - _FEATURE_DATA_CORE
 - ntddmmc/_FEATURE_DATA_CORE
 - PFEATURE_DATA_CORE
 - ntddmmc/PFEATURE_DATA_CORE
 - FEATURE_DATA_CORE
 - ntddmmc/FEATURE_DATA_CORE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - _FEATURE_DATA_CORE
 - PFEATURE_DATA_CORE
 - FEATURE_DATA_CORE
---

# FEATURE_DATA_CORE structure

## -description

The **FEATURE_DATA_CORE** structure holds data for the feature named "Core" by the *Multimedia Commands - 3 (MMC-3)* specification.

## -struct-fields

### -field Header

Contains a [**FEATURE_HEADER**](ns-ntddmmc-_feature_header.md) structure with header information for this feature descriptor.

### -field PhysicalInterface

Must be set to the current communication path between initiator and device, as defined in the *Multimedia Commands - 4 (MMC-4)* specification. The bytes of this array are arranged in big-endian order. **PhysicalInterface**[0] contains the most significant byte, and **PhysicalInterface**[3] contains the least significant byte.

### -field DeviceBusyEvent

Value that specifies a *Device Busy Event* Descriptor, as defined in the *Multimedia Commands - 4 (MMC-4)* specification. Device busy events notify the initiator of commands that are executing but that require an abnormally long time to complete.

### -field INQUIRY2

Value that specifies the INQUIRY command operation code, as defined in the *Multimedia Commands - 4 (MMC-4)* specification.

### -field Reserved1

Reserved; do not use.

### -field Reserved2

Reserved; do not use.

## -remarks

The MMC-3 Core feature encompasses the basic functionality which is mandatory for all devices that support the *MMC-3* standard. See the *MMC-3* specification for a description of the capabilities included in the Core feature.

## -see-also

[**FEATURE_HEADER**](ns-ntddmmc-_feature_header.md)

[**FEATURE_NUMBER**](ne-ntddmmc-_feature_number.md)
