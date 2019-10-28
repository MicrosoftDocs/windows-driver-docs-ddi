---
UID: NS:ntddmmc._FEATURE_DATA_MRW
title: _FEATURE_DATA_MRW (ntddmmc.h)
description: The FEATURE_DATA_MRW structure contains information about the MRW feature.
old-location: storage\feature_data_mrw.htm
tech.root: storage
ms.assetid: af0c8c50-c5a0-4395-a608-fced6ac3cfe5
ms.date: 03/29/2018
ms.keywords: "*PFEATURE_DATA_MRW, FEATURE_DATA_MRW, FEATURE_DATA_MRW structure [Storage Devices], PFEATURE_DATA_MRW, PFEATURE_DATA_MRW structure pointer [Storage Devices], _FEATURE_DATA_MRW, ntddmmc/FEATURE_DATA_MRW, ntddmmc/PFEATURE_DATA_MRW, storage.feature_data_mrw, structs-CD-ROM_54208a52-0bc2-4e97-a3b1-4d57f5192ce4.xml"
ms.topic: struct
f1_keywords:
 - "ntddmmc/FEATURE_DATA_MRW"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddmmc.h
api_name:
- FEATURE_DATA_MRW
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_MRW, *PFEATURE_DATA_MRW
---

# _FEATURE_DATA_MRW structure


## -description


The FEATURE_DATA_MRW structure contains information about the MRW feature. 


## -struct-fields




### -field Header

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Write

Indicates, if set to 1, that the device can format discs using the MRW format and write to discs that have been formatted in this manner. See the <i>SCSI Multimedia - 4 (MMC-4)</i> specification for more information. 


### -field DvdPlusRead


### -field DvdPlusWrite


### -field Reserved01


### -field Reserved2

Reserved. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>
 

 

