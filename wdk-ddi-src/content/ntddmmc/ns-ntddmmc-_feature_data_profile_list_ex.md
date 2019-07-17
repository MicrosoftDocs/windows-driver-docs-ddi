---
UID: NS:ntddmmc._FEATURE_DATA_PROFILE_LIST_EX
title: _FEATURE_DATA_PROFILE_LIST_EX (ntddmmc.h)
description: The FEATURE_DATA_PROFILE_LIST_EX structure contains information corresponding to a profile list element in a profile list descriptor.
old-location: storage\feature_data_profile_list_ex.htm
tech.root: storage
ms.assetid: c15f9be2-1f35-41cf-a1de-880e3662f2b4
ms.date: 03/29/2018
ms.keywords: "*PFEATURE_DATA_PROFILE_LIST_EX, FEATURE_DATA_PROFILE_LIST_EX, FEATURE_DATA_PROFILE_LIST_EX structure [Storage Devices], PFEATURE_DATA_PROFILE_LIST_EX, PFEATURE_DATA_PROFILE_LIST_EX structure pointer [Storage Devices], _FEATURE_DATA_PROFILE_LIST_EX, ntddmmc/FEATURE_DATA_PROFILE_LIST_EX, ntddmmc/PFEATURE_DATA_PROFILE_LIST_EX, storage.feature_data_profile_list_ex, structs-CD-ROM_4834760d-aeb7-44eb-a8a7-4c961ff8aa4c.xml"
ms.topic: struct
f1_keywords:
 - "ntddmmc/FEATURE_DATA_PROFILE_LIST_EX"
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
- FEATURE_DATA_PROFILE_LIST_EX
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_PROFILE_LIST_EX, *PFEATURE_DATA_PROFILE_LIST_EX
---

# _FEATURE_DATA_PROFILE_LIST_EX structure


## -description


The FEATURE_DATA_PROFILE_LIST_EX structure contains information corresponding to a profile list element in a profile list descriptor. 


## -struct-fields




### -field ProfileNumber

Contains the profile number. This number must be one of the values defined by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddmmc/ne-ntddmmc-_feature_profile_type">FEATURE_PROFILE_TYPE</a> enumeration. <b>ProfileNumber</b>[0] must contain the most significant byte of the profile number. <b>ProfileNumber</b>[1] must contain the least significant byte. 


### -field Current

Indicates, when set to 1, that this feature is currently active and the feature data is valid. When set to zero, this bit indicates that the feature is not currently active and that the feature data might not be valid. 


### -field Reserved1

Reserved. 


### -field Reserved2

Reserved. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddmmc/ns-ntddmmc-_feature_data_profile_list">FEATURE_DATA_PROFILE_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddmmc/ne-ntddmmc-_feature_profile_type">FEATURE_PROFILE_TYPE</a>
 

 

