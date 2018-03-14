---
UID: NS:ntddmmc._FEATURE_DATA_SECTOR_ERASABLE
title: "_FEATURE_DATA_SECTOR_ERASABLE"
author: windows-driver-content
description: The FEATURE_DATA_SECTOR_ERASABLE structure contains information for the Sector Erasable feature.
old-location: storage\feature_data_sector_erasable.htm
old-project: storage
ms.assetid: 6f714e13-a844-4afa-9002-52a5318a7659
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_SECTOR_ERASABLE, FEATURE_DATA_SECTOR_ERASABLE, FEATURE_DATA_SECTOR_ERASABLE structure [Storage Devices], PFEATURE_DATA_SECTOR_ERASABLE, PFEATURE_DATA_SECTOR_ERASABLE structure pointer [Storage Devices], _FEATURE_DATA_SECTOR_ERASABLE, ntddmmc/FEATURE_DATA_SECTOR_ERASABLE, ntddmmc/PFEATURE_DATA_SECTOR_ERASABLE, storage.feature_data_sector_erasable, structs-CD-ROM_e48f2e10-1b6d-4d5a-9e8d-b1fc45fd8509.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddmmc.h
api_name:
-	FEATURE_DATA_SECTOR_ERASABLE
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_SECTOR_ERASABLE, *PFEATURE_DATA_SECTOR_ERASABLE
---

# _FEATURE_DATA_SECTOR_ERASABLE structure


## -description


The FEATURE_DATA_SECTOR_ERASABLE structure contains information for the Sector Erasable feature. 


## -syntax


````
typedef struct _FEATURE_DATA_SECTOR_ERASABLE {
  FEATURE_HEADER Header;
} FEATURE_DATA_SECTOR_ERASABLE, *PFEATURE_DATA_SECTOR_ERASABLE;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


## -remarks



This structure holds data for the feature named "Sector Erasable" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can erase media. These devices also require an erase pass before overwriting existing data.

When queried, devices supporting this feature must return the information indicated in <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>. No other feature-specific information is required. 




## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 


