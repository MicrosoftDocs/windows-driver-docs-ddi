---
UID: NS:ntddmmc._FEATURE_DATA_MULTI_READ
title: "_FEATURE_DATA_MULTI_READ"
author: windows-driver-content
description: The FEATURE_DATA_MULTI_READ structure contains data for the multiread feature.
old-location: storage\feature_data_multi_read.htm
old-project: storage
ms.assetid: a7db6bd2-7c04-4bfc-b4b4-db1f99520e56
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_MULTI_READ, FEATURE_DATA_MULTI_READ, FEATURE_DATA_MULTI_READ structure [Storage Devices], PFEATURE_DATA_MULTI_READ, PFEATURE_DATA_MULTI_READ structure pointer [Storage Devices], _FEATURE_DATA_MULTI_READ, ntddmmc/FEATURE_DATA_MULTI_READ, ntddmmc/PFEATURE_DATA_MULTI_READ, storage.feature_data_multi_read, structs-CD-ROM_687fe1cb-1667-4650-97c5-d6e4af7df2af.xml"
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
-	FEATURE_DATA_MULTI_READ
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_MULTI_READ, *PFEATURE_DATA_MULTI_READ
---

# _FEATURE_DATA_MULTI_READ structure


## -description


The FEATURE_DATA_MULTI_READ structure contains data for the multiread feature. 


## -syntax


````
typedef struct _FEATURE_DATA_MULTI_READ {
  FEATURE_HEADER Header;
} FEATURE_DATA_MULTI_READ, *PFEATURE_DATA_MULTI_READ;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


## -remarks



This structure holds data for the feature named "MultiRead," originally defined by the Optical Storage Technology Association (OSTA) and incorporated into the <i>MMC-3 </i>specification. Devices that support this feature can read all CD media types. 

When queried, devices supporting this feature must return the information indicated in <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>. No other feature-specific information is required. 




## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_MULTI_READ structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

