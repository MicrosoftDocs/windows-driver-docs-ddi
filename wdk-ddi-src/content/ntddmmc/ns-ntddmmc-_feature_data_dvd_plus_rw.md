---
UID: NS:ntddmmc._FEATURE_DATA_DVD_PLUS_RW
title: _FEATURE_DATA_DVD_PLUS_RW (ntddmmc.h)
description: The FEATURE_DATA_DVD_PLUS_RW structure contains information about the DVD+RW feature.
old-location: storage\feature_data_dvd_plus_rw.htm
tech.root: storage
ms.assetid: 55cbef36-dea7-4f7c-ac43-fb819b61a858
ms.date: 03/29/2018
keywords: ["FEATURE_DATA_DVD_PLUS_RW structure"]
ms.keywords: "*PFEATURE_DATA_DVD_PLUS_RW, FEATURE_DATA_DVD_PLUS_RW, FEATURE_DATA_DVD_PLUS_RW structure [Storage Devices], PFEATURE_DATA_DVD_PLUS_RW, PFEATURE_DATA_DVD_PLUS_RW structure pointer [Storage Devices], _FEATURE_DATA_DVD_PLUS_RW, ntddmmc/FEATURE_DATA_DVD_PLUS_RW, ntddmmc/PFEATURE_DATA_DVD_PLUS_RW, storage.feature_data_dvd_plus_rw, structs-CD-ROM_8b49bf86-5e1a-42a3-9bb6-ba6afca60375.xml"
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
req.typenames: FEATURE_DATA_DVD_PLUS_RW, *PFEATURE_DATA_DVD_PLUS_RW
f1_keywords:
 - _FEATURE_DATA_DVD_PLUS_RW
 - ntddmmc/_FEATURE_DATA_DVD_PLUS_RW
 - PFEATURE_DATA_DVD_PLUS_RW
 - ntddmmc/PFEATURE_DATA_DVD_PLUS_RW
 - FEATURE_DATA_DVD_PLUS_RW
 - ntddmmc/FEATURE_DATA_DVD_PLUS_RW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - FEATURE_DATA_DVD_PLUS_RW
---

# _FEATURE_DATA_DVD_PLUS_RW structure


## -description

The FEATURE_DATA_DVD_PLUS_RW structure contains information about the DVD+RW feature.

## -struct-fields

### -field Header

Contains a <a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor.

### -field Write

Indicates, when set to 1, that the device can do background formatting of DVD+RW discs according to <i>DVD+RW 4.7 Gbytes Basic Format Specifications</i>, and can write to discs that have been formatted in this manner.

### -field Reserved1

Reserved.

### -field CloseOnly

Indicates, when set to 1, then the device supports only read compatibility stops. When set to 0, the device supports both forms of background format stop. For more information about background format stops, see the <i>SCSI Multimedia Commands - 4 (MMC-4)</i> specification published by the American National Standards Institute (ANSI).

### -field QuickStart

### -field Reserved02

### -field Reserved03

## -remarks

This structure holds data for the feature named "DVD+RW" by the <i>SCSI Multimedia - 4 (MMC-4) </i>specification. Devices that support this feature can read a recorded DVD+RW disc that is formatted according to the <i>DVD+RW 4.7 Gbytes Basic Format Specification. </i>

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>