---
UID: NS:ntddmmc._FEATURE_DATA_FORMATTABLE
title: "_FEATURE_DATA_FORMATTABLE"
author: windows-driver-content
description: The FEATURE_DATA_FORMATTABLE structure contains information for the Formattable feature.
old-location: storage\feature_data_formattable.htm
old-project: storage
ms.assetid: 658ea6a4-309d-4f78-9a02-f93e7d945325
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_FORMATTABLE, FEATURE_DATA_FORMATTABLE, FEATURE_DATA_FORMATTABLE structure [Storage Devices], PFEATURE_DATA_FORMATTABLE, PFEATURE_DATA_FORMATTABLE structure pointer [Storage Devices], _FEATURE_DATA_FORMATTABLE, ntddmmc/FEATURE_DATA_FORMATTABLE, ntddmmc/PFEATURE_DATA_FORMATTABLE, storage.feature_data_formattable, structs-CD-ROM_27503157-de29-4c39-bb7a-b17528984f7f.xml"
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
-	FEATURE_DATA_FORMATTABLE
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_FORMATTABLE, *PFEATURE_DATA_FORMATTABLE
---

# _FEATURE_DATA_FORMATTABLE structure


## -description


The FEATURE_DATA_FORMATTABLE structure contains information for the Formattable feature. 


## -syntax


````
typedef struct _FEATURE_DATA_FORMATTABLE {
  FEATURE_HEADER Header;
  UCHAR          FullCertification  :1;
  UCHAR          QuickCertification  :1;
  UCHAR          SpareAreaExpansion  :1;
  UCHAR          RENoSpareAllocated  :1;
  UCHAR          Reserved1  :4;
  UCHAR          Reserved2[3];
  UCHAR          RRandomWritable  :1;
  UCHAR          Reserved3  :7;
  UCHAR          Reserved4[3];
} FEATURE_DATA_FORMATTABLE, *PFEATURE_DATA_FORMATTABLE;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


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

When queried, devices supporting this feature must return the information indicated in <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>. No other feature-specific information is required. 




## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 


