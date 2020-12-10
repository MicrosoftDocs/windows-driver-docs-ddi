---
UID: NS:ntddmmc._FEATURE_DATA_MRW
title: _FEATURE_DATA_MRW (ntddmmc.h)
description: The FEATURE_DATA_MRW structure contains information about the MRW feature.
old-location: storage\feature_data_mrw.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["FEATURE_DATA_MRW structure"]
ms.keywords: "*PFEATURE_DATA_MRW, FEATURE_DATA_MRW, FEATURE_DATA_MRW structure [Storage Devices], PFEATURE_DATA_MRW, PFEATURE_DATA_MRW structure pointer [Storage Devices], _FEATURE_DATA_MRW, ntddmmc/FEATURE_DATA_MRW, ntddmmc/PFEATURE_DATA_MRW, storage.feature_data_mrw, structs-CD-ROM_54208a52-0bc2-4e97-a3b1-4d57f5192ce4.xml"
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
req.typenames: FEATURE_DATA_MRW, *PFEATURE_DATA_MRW
f1_keywords:
 - _FEATURE_DATA_MRW
 - ntddmmc/_FEATURE_DATA_MRW
 - PFEATURE_DATA_MRW
 - ntddmmc/PFEATURE_DATA_MRW
 - FEATURE_DATA_MRW
 - ntddmmc/FEATURE_DATA_MRW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - FEATURE_DATA_MRW
---

# _FEATURE_DATA_MRW structure


## -description

The FEATURE_DATA_MRW structure contains information about the MRW feature.

## -struct-fields

### -field Header

Contains a <a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor.

### -field Write

Indicates, if set to 1, that the device can format discs using the MRW format and write to discs that have been formatted in this manner. See the <i>SCSI Multimedia - 4 (MMC-4)</i> specification for more information.

### -field DvdPlusRead

### -field DvdPlusWrite

### -field Reserved01

### -field Reserved2

Reserved.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>
