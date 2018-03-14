---
UID: NS:ntddmmc._FEATURE_DATA_RESTRICTED_OVERWRITE
title: "_FEATURE_DATA_RESTRICTED_OVERWRITE"
author: windows-driver-content
description: The FEATURE_DATA_RESTRICTED_OVERWRITE structure holds information about the Restricted Overwrite feature.
old-location: storage\feature_data_restricted_overwrite.htm
old-project: storage
ms.assetid: d9f3e892-1ed5-4030-a656-7d2d294b1c82
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_RESTRICTED_OVERWRITE, FEATURE_DATA_RESTRICTED_OVERWRITE, FEATURE_DATA_RESTRICTED_OVERWRITE structure [Storage Devices], PFEATURE_DATA_RESTRICTED_OVERWRITE, PFEATURE_DATA_RESTRICTED_OVERWRITE structure pointer [Storage Devices], _FEATURE_DATA_RESTRICTED_OVERWRITE, ntddmmc/FEATURE_DATA_RESTRICTED_OVERWRITE, ntddmmc/PFEATURE_DATA_RESTRICTED_OVERWRITE, storage.feature_data_restricted_overwrite, structs-CD-ROM_d2d9725b-16c9-4361-a2fc-90bdc2d7905c.xml"
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
-	FEATURE_DATA_RESTRICTED_OVERWRITE
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_RESTRICTED_OVERWRITE, *PFEATURE_DATA_RESTRICTED_OVERWRITE
---

# _FEATURE_DATA_RESTRICTED_OVERWRITE structure


## -description


The FEATURE_DATA_RESTRICTED_OVERWRITE structure holds information about the Restricted Overwrite feature. 


## -syntax


````
typedef struct _FEATURE_DATA_RESTRICTED_OVERWRITE {
  FEATURE_HEADER Header;
} FEATURE_DATA_RESTRICTED_OVERWRITE, *PFEATURE_DATA_RESTRICTED_OVERWRITE;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.


## -remarks



This structure holds data for the feature named "Restricted Overwrite" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can only overwrite a limited set of logical blocks at any given time. 

When queried, devices supporting this feature must return the information indicated in <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>. No other feature-specific information is required. 




## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_RESTRICTED_OVERWRITE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

