---
UID: NS:ntddmmc._FEATURE_DATA_DVD_CPRM
title: _FEATURE_DATA_DVD_CPRM (ntddmmc.h)
description: The FEATURE_DATA_DVD_CPRM structure holds information about the DVD Content Protection for Recorded Media (CPRM) feature.
old-location: storage\feature_data_dvd_cprm.htm
tech.root: storage
ms.assetid: 060c1e9a-14d3-4f9b-b898-d8042f5efd7e
ms.date: 03/29/2018
keywords: ["FEATURE_DATA_DVD_CPRM structure"]
ms.keywords: "*PFEATURE_DATA_DVD_CPRM, FEATURE_DATA_DVD_CPRM, FEATURE_DATA_DVD_CPRM structure [Storage Devices], PFEATURE_DATA_DVD_CPRM, PFEATURE_DATA_DVD_CPRM structure pointer [Storage Devices], _FEATURE_DATA_DVD_CPRM, ntddmmc/FEATURE_DATA_DVD_CPRM, ntddmmc/PFEATURE_DATA_DVD_CPRM, storage.feature_data_dvd_cprm, structs-CD-ROM_376d4f99-5d92-48ad-b126-d1f6858e7fac.xml"
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
req.typenames: FEATURE_DATA_DVD_CPRM, *PFEATURE_DATA_DVD_CPRM
f1_keywords:
 - _FEATURE_DATA_DVD_CPRM
 - ntddmmc/_FEATURE_DATA_DVD_CPRM
 - PFEATURE_DATA_DVD_CPRM
 - ntddmmc/PFEATURE_DATA_DVD_CPRM
 - FEATURE_DATA_DVD_CPRM
 - ntddmmc/FEATURE_DATA_DVD_CPRM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - FEATURE_DATA_DVD_CPRM
---

# _FEATURE_DATA_DVD_CPRM structure


## -description

The FEATURE_DATA_DVD_CPRM structure holds information about the DVD Content Protection for Recorded Media (CPRM) feature.

## -struct-fields

### -field Header

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor.

### -field Reserved0

Reserved.

### -field CPRMVersion

Contains the CPRM version number. Must be set to 1.

## -remarks

This structure holds data for the feature named "DVD CPRM" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can perform DVD Content Protection for Recordable Media (CPRM) authentication and key management.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>

