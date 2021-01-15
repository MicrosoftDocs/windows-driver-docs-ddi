---
UID: NS:ntddmmc._FEATURE_DATA_CD_READ
title: _FEATURE_DATA_CD_READ (ntddmmc.h)
description: The FEATURE_DATA_CD_READ structure contains information about the CD Read feature.
old-location: storage\feature_data_cd_read.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["FEATURE_DATA_CD_READ structure"]
ms.keywords: "*PFEATURE_DATA_CD_READ, FEATURE_DATA_CD_READ, FEATURE_DATA_CD_READ structure [Storage Devices], PFEATURE_DATA_CD_READ, PFEATURE_DATA_CD_READ structure pointer [Storage Devices], _FEATURE_DATA_CD_READ, ntddmmc/FEATURE_DATA_CD_READ, ntddmmc/PFEATURE_DATA_CD_READ, storage.feature_data_cd_read, structs-CD-ROM_8b31a56d-f370-4b85-8f37-a88041276a20.xml"
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
req.typenames: FEATURE_DATA_CD_READ, *PFEATURE_DATA_CD_READ
f1_keywords:
 - _FEATURE_DATA_CD_READ
 - ntddmmc/_FEATURE_DATA_CD_READ
 - PFEATURE_DATA_CD_READ
 - ntddmmc/PFEATURE_DATA_CD_READ
 - FEATURE_DATA_CD_READ
 - ntddmmc/FEATURE_DATA_CD_READ
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - _FEATURE_DATA_CD_READ
 - PFEATURE_DATA_CD_READ
 - FEATURE_DATA_CD_READ
---

# _FEATURE_DATA_CD_READ structure


## -description

The FEATURE_DATA_CD_READ structure contains information about the CD Read feature.

## -struct-fields

### -field Header

Contains a <a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor.

### -field CDText

Indicates, when set to 1, that the device supports format code 0x05 of the READ/TOC/PMA/ATIP command, as defined in the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. When set to zero, CD-Text is not supported.

### -field C2ErrorData

Indicates, when set to 1, that the device supports the C2 error pointers as described in the <i>MMC-3 </i>specification. When set to zero, it indicates that the device does not support C2 error pointers.

### -field Reserved01

### -field DigitalAudioPlay

### -field Reserved2

Reserved.

## -remarks

This structure holds data for the feature named "CD Read" by the <i>MMC-3 </i>specification. Devices that support this feature can read CD-specific information from the media and can read user data from all types of CD blocks.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>

