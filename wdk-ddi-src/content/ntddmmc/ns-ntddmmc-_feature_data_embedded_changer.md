---
UID: NS:ntddmmc._FEATURE_DATA_EMBEDDED_CHANGER
title: _FEATURE_DATA_EMBEDDED_CHANGER (ntddmmc.h)
description: The FEATURE_DATA_EMBEDDED_CHANGER structure holds data for the Embedded Changer feature.
old-location: storage\feature_data_embedded_changer.htm
tech.root: storage
ms.assetid: 1335d1fa-af96-4a31-a1cf-266f7a3325ef
ms.date: 03/29/2018
keywords: ["_FEATURE_DATA_EMBEDDED_CHANGER structure"]
ms.keywords: "*PFEATURE_DATA_EMBEDDED_CHANGER, FEATURE_DATA_EMBEDDED_CHANGER, FEATURE_DATA_EMBEDDED_CHANGER structure [Storage Devices], PFEATURE_DATA_EMBEDDED_CHANGER, PFEATURE_DATA_EMBEDDED_CHANGER structure pointer [Storage Devices], _FEATURE_DATA_EMBEDDED_CHANGER, ntddmmc/FEATURE_DATA_EMBEDDED_CHANGER, ntddmmc/PFEATURE_DATA_EMBEDDED_CHANGER, storage.feature_data_embedded_changer, structs-CD-ROM_655edb8d-6748-4d10-8cd9-51b3a696bccd.xml"
f1_keywords:
 - "ntddmmc/FEATURE_DATA_EMBEDDED_CHANGER"
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
- FEATURE_DATA_EMBEDDED_CHANGER
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_EMBEDDED_CHANGER, *PFEATURE_DATA_EMBEDDED_CHANGER
---

# _FEATURE_DATA_EMBEDDED_CHANGER structure


## -description


The FEATURE_DATA_EMBEDDED_CHANGER structure holds data for the Embedded Changer feature. 


## -struct-fields




### -field Header

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Reserved1

Reserved. 


### -field SupportsDiscPresent

Indicates, when set to 1, that the device can report the contents of the slots after a reset or magazine change. When set to zero, this bit indicates that the device can report the contents of the slots after reset or magazine change. 


### -field Reserved2

Reserved. 


### -field SideChangeCapable

Indicates, when set to 1, that the device is capable of selecting both sides of the media. When set to zero, this bit indicates that the device is not capable of selecting both sides of the media. 


### -field Reserved3

Reserved.


### -field Reserved4

Reserved.


### -field HighestSlotNumber

Indicates the number of slots minus 1. 


### -field Reserved

Reserved.


## -remarks



This structure holds data for the feature named "Embedded Changer" by the <i>SCSI Multimedia - 4 (MMC-4) </i>specification. Devices that support this feature can move media back and forth between a media storage area and the mechanism that actually accesses the media.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>
 

 

