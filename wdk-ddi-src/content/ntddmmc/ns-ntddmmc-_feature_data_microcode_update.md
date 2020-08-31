---
UID: NS:ntddmmc._FEATURE_DATA_MICROCODE_UPDATE
title: _FEATURE_DATA_MICROCODE_UPDATE (ntddmmc.h)
description: The FEATURE_DATA_MICROCODE_UPDATE structure holds information about the Microcode Upgrade feature.
old-location: storage\feature_data_microcode_update.htm
tech.root: storage
ms.assetid: ff9f959b-6901-43b8-b335-c0286136b747
ms.date: 03/29/2018
keywords: ["FEATURE_DATA_MICROCODE_UPDATE structure"]
ms.keywords: "*PFEATURE_DATA_MICROCODE_UPDATE, FEATURE_DATA_MICROCODE_UPDATE, FEATURE_DATA_MICROCODE_UPDATE structure [Storage Devices], PFEATURE_DATA_MICROCODE_UPDATE, PFEATURE_DATA_MICROCODE_UPDATE structure pointer [Storage Devices], _FEATURE_DATA_MICROCODE_UPDATE, ntddmmc/FEATURE_DATA_MICROCODE_UPDATE, ntddmmc/PFEATURE_DATA_MICROCODE_UPDATE, storage.feature_data_microcode_update, structs-CD-ROM_e2dbda29-d727-4736-93bd-0e115b9d7948.xml"
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
req.typenames: FEATURE_DATA_MICROCODE_UPDATE, *PFEATURE_DATA_MICROCODE_UPDATE
f1_keywords:
 - _FEATURE_DATA_MICROCODE_UPDATE
 - ntddmmc/_FEATURE_DATA_MICROCODE_UPDATE
 - PFEATURE_DATA_MICROCODE_UPDATE
 - ntddmmc/PFEATURE_DATA_MICROCODE_UPDATE
 - FEATURE_DATA_MICROCODE_UPDATE
 - ntddmmc/FEATURE_DATA_MICROCODE_UPDATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - FEATURE_DATA_MICROCODE_UPDATE
---

# _FEATURE_DATA_MICROCODE_UPDATE structure


## -description

The FEATURE_DATA_MICROCODE_UPDATE structure holds information about the Microcode Upgrade feature.

## -struct-fields

### -field Header

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor.

### -field M5

### -field Reserved1

### -field Reserved2

## -remarks

This structure holds data for the feature named "Microcode Upgrade" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can upgrade their internal microcode by means of a published interface. 

When queried, devices supporting this feature must return the information indicated in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>. No other feature-specific information is required.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>

