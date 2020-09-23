---
UID: NS:ntddmmc._FEATURE_DATA_FORMATTABLE
title: _FEATURE_DATA_FORMATTABLE (ntddmmc.h)
description: The FEATURE_DATA_FORMATTABLE structure contains information for the Formattable feature.
old-location: storage\feature_data_formattable.htm
tech.root: storage
ms.assetid: 658ea6a4-309d-4f78-9a02-f93e7d945325
ms.date: 03/29/2018
keywords: ["FEATURE_DATA_FORMATTABLE structure"]
ms.keywords: "*PFEATURE_DATA_FORMATTABLE, FEATURE_DATA_FORMATTABLE, FEATURE_DATA_FORMATTABLE structure [Storage Devices], PFEATURE_DATA_FORMATTABLE, PFEATURE_DATA_FORMATTABLE structure pointer [Storage Devices], _FEATURE_DATA_FORMATTABLE, ntddmmc/FEATURE_DATA_FORMATTABLE, ntddmmc/PFEATURE_DATA_FORMATTABLE, storage.feature_data_formattable, structs-CD-ROM_27503157-de29-4c39-bb7a-b17528984f7f.xml"
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
req.typenames: FEATURE_DATA_FORMATTABLE, *PFEATURE_DATA_FORMATTABLE
f1_keywords:
 - _FEATURE_DATA_FORMATTABLE
 - ntddmmc/_FEATURE_DATA_FORMATTABLE
 - PFEATURE_DATA_FORMATTABLE
 - ntddmmc/PFEATURE_DATA_FORMATTABLE
 - FEATURE_DATA_FORMATTABLE
 - ntddmmc/FEATURE_DATA_FORMATTABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - FEATURE_DATA_FORMATTABLE
---

# _FEATURE_DATA_FORMATTABLE structure


## -description

The FEATURE_DATA_FORMATTABLE structure contains information for the Formattable feature.

## -struct-fields

### -field Header

Contains a <a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor.

### -field FullCertification

### -field QuickCertification

### -field SpareAreaExpansion

### -field RENoSpareAllocated

### -field Reserved1

### -field Reserved2

### -field RRandomWritable

### -field Reserved3

### -field Reserved4

## -remarks

This structure holds data for the feature named "Formattable" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can format media into logical blocks. 

When queried, devices supporting this feature must return the information indicated in <a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>. No other feature-specific information is required.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>