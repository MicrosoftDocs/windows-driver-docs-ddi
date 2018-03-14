---
UID: NS:ntddmmc._FEATURE_DATA_DVD_CSS
title: "_FEATURE_DATA_DVD_CSS"
author: windows-driver-content
description: The FEATURE_DATA_DVD_CSS structure holds information about the DVD Content Scrambling System (CSS) feature.
old-location: storage\feature_data_dvd_css.htm
old-project: storage
ms.assetid: 8266f17d-65d6-49a0-a8ea-fee71dff4db0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_DVD_CSS, FEATURE_DATA_DVD_CSS, FEATURE_DATA_DVD_CSS structure [Storage Devices], PFEATURE_DATA_DVD_CSS, PFEATURE_DATA_DVD_CSS structure pointer [Storage Devices], _FEATURE_DATA_DVD_CSS, ntddmmc/FEATURE_DATA_DVD_CSS, ntddmmc/PFEATURE_DATA_DVD_CSS, storage.feature_data_dvd_css, structs-CD-ROM_1508ce84-fa86-423e-a6c1-4059bf0cb54c.xml"
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
-	FEATURE_DATA_DVD_CSS
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_DVD_CSS, *PFEATURE_DATA_DVD_CSS
---

# _FEATURE_DATA_DVD_CSS structure


## -description


The FEATURE_DATA_DVD_CSS structure holds information about the DVD Content Scrambling System (CSS) feature.


## -syntax


````
typedef struct _FEATURE_DATA_DVD_CSS {
  FEATURE_HEADER Header;
  UCHAR          Reserved1[3];
  UCHAR          CssVersion;
} FEATURE_DATA_DVD_CSS, *PFEATURE_DATA_DVD_CSS;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Reserved1

Reserved. 


### -field CssVersion

Must be set to 1. 


## -remarks



This structure holds data for the feature named "DVD-CSS" by the <i>MMC-3 </i>specification. Devices that support this feature can perform DVD Content Scrambling System (DVD-CSS) authentication and key management. 




## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 


