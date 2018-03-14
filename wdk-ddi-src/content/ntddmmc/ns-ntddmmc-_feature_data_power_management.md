---
UID: NS:ntddmmc._FEATURE_DATA_POWER_MANAGEMENT
title: "_FEATURE_DATA_POWER_MANAGEMENT"
author: windows-driver-content
description: The FEATURE_DATA_POWER_MANAGEMENT structure holds information about the Power Management feature.
old-location: storage\feature_data_power_management.htm
old-project: storage
ms.assetid: 0b3f23d1-1081-4fb9-86af-6dbf7bfeb3b7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_POWER_MANAGEMENT, FEATURE_DATA_POWER_MANAGEMENT, FEATURE_DATA_POWER_MANAGEMENT structure [Storage Devices], PFEATURE_DATA_POWER_MANAGEMENT, PFEATURE_DATA_POWER_MANAGEMENT structure pointer [Storage Devices], _FEATURE_DATA_POWER_MANAGEMENT, ntddmmc/FEATURE_DATA_POWER_MANAGEMENT, ntddmmc/PFEATURE_DATA_POWER_MANAGEMENT, storage.feature_data_power_management, structs-CD-ROM_b2dfa21c-3dd3-40fd-9605-05c36c4b9fc8.xml"
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
-	FEATURE_DATA_POWER_MANAGEMENT
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_POWER_MANAGEMENT, *PFEATURE_DATA_POWER_MANAGEMENT
---

# _FEATURE_DATA_POWER_MANAGEMENT structure


## -description


The FEATURE_DATA_POWER_MANAGEMENT structure holds information about the Power Management feature.


## -syntax


````
typedef struct _FEATURE_DATA_POWER_MANAGEMENT {
  FEATURE_HEADER Header;
} FEATURE_DATA_POWER_MANAGEMENT, *PFEATURE_DATA_POWER_MANAGEMENT;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


## -remarks



This structure holds data for the feature named "Power Management" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can perform both initiator and logical-unit directed power management.

When queried, devices supporting this feature must return the information indicated in <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>. No other feature-specific information is required. 




## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 


