---
UID: NS:ntddmmc._FEATURE_HEADER
title: _FEATURE_HEADER (ntddmmc.h)
description: The FEATURE_HEADER structure is used in conjunction with the IOCTL_CDROM_GET_CONFIGURATION request to report header information for both feature and profile descriptors.
old-location: storage\feature_header.htm
tech.root: storage
ms.assetid: 61831fbb-48ad-4831-8b69-7b1a5cafa629
ms.date: 03/29/2018
ms.keywords: "*PFEATURE_HEADER, FEATURE_HEADER, FEATURE_HEADER structure [Storage Devices], PFEATURE_HEADER, PFEATURE_HEADER structure pointer [Storage Devices], _FEATURE_HEADER, ntddmmc/FEATURE_HEADER, ntddmmc/PFEATURE_HEADER, storage.feature_header, structs-CD-ROM_41d7886f-d383-4416-8f89-b40f1bb0bc7f.xml"
f1_keywords:
 - "ntddmmc/FEATURE_HEADER"
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
- FEATURE_HEADER
product:
- Windows
targetos: Windows
req.typenames: FEATURE_HEADER, *PFEATURE_HEADER
---

# _FEATURE_HEADER structure


## -description


The FEATURE_HEADER structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_configuration">IOCTL_CDROM_GET_CONFIGURATION</a> request to report header information for both feature and profile descriptors.


## -struct-fields




### -field FeatureCode

Contains a value between zero and 0xffff that indicates a feature. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a> enumeration provides a list of currently supported feature numbers. <b>FeatureCode</b>[0] contains the most significant byte of the feature number. <b>FeatureCode</b>[1] contains the least significant byte. 


### -field Current

Indicates, when set to 1, that this feature is currently active and the data reported for the feature is valid. When set to zero, this bit indicates that the feature is not currently active and that the data reported for the feature might not be valid. 


### -field Persistent

Indicates, when set to 1, that the feature is always active. When set to zero, this bit indicates that the feature is not always active. 


### -field Version

Must be set to zero unless otherwise specified within the description for a particular feature.


### -field Reserved0

Reserved.


### -field AdditionalLength

Indicates the number of bytes of feature information that follow this header. This member must be an integral multiple of 4. The total size of the data related to this feature will be <b>AdditionalLength</b> + <b>sizeof</b>(FEATURE_HEADER).


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_get_configuration_header">GET_CONFIGURATION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_configuration">IOCTL_CDROM_GET_CONFIGURATION</a>
 

 

