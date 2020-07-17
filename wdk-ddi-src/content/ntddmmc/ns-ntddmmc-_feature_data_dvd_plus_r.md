---
UID: NS:ntddmmc._FEATURE_DATA_DVD_PLUS_R
title: _FEATURE_DATA_DVD_PLUS_R (ntddmmc.h)
description: The FEATURE_DATA_DVD_PLUS_R structure contains information about the DVD+R feature.
old-location: storage\feature_data_dvd_plus_r.htm
tech.root: storage
ms.assetid: e1501ea9-a55b-4fbc-990b-2172c7369bb1
ms.date: 03/29/2018
keywords: ["_FEATURE_DATA_DVD_PLUS_R structure"]
ms.keywords: "*PFEATURE_DATA_DVD_PLUS_R, FEATURE_DATA_DVD_PLUS_R, FEATURE_DATA_DVD_PLUS_R structure [Storage Devices], PFEATURE_DATA_DVD_PLUS_R, PFEATURE_DATA_DVD_PLUS_R structure pointer [Storage Devices], _FEATURE_DATA_DVD_PLUS_R, ntddmmc/FEATURE_DATA_DVD_PLUS_R, ntddmmc/PFEATURE_DATA_DVD_PLUS_R, storage.feature_data_dvd_plus_r, structs-CD-ROM_fb4a1383-3c8f-48e8-8fc8-3796e00f80a6.xml"
f1_keywords:
 - "ntddmmc/FEATURE_DATA_DVD_PLUS_R"
 - "FEATURE_DATA_DVD_PLUS_R"
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
- FEATURE_DATA_DVD_PLUS_R
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_DVD_PLUS_R, *PFEATURE_DATA_DVD_PLUS_R
---

# _FEATURE_DATA_DVD_PLUS_R structure


## -description


The FEATURE_DATA_DVD_PLUS_R structure contains information about the DVD+R feature. 


## -struct-fields




### -field Header

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Write

Indicates, when set to 1, that the device has an ability that was not specified in the DVD-ROM profile, to write to DVD+R discs according to <i>DVD+R 4.7 Gbytes Basic Format Specifications.</i> When set to 0, the device has no extra ability beyond what is specified in the profile. 


### -field Reserved1

Reserved. 


### -field Reserved2

Reserved. 


## -remarks



This structure holds data for the feature named "DVD+R" by the <i>MMC-3 </i>specification. Devices that support this feature can specify whether they are able to perform writes to DVD+R discs, even though this ability was not indicated in the device's DVD-ROM profile.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>
 

 

