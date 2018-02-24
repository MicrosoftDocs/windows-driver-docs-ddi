---
UID: NS:ntddmmc._FEATURE_DATA_DVD_CSS
title: "_FEATURE_DATA_DVD_CSS"
author: windows-driver-content
description: The FEATURE_DATA_DVD_CSS structure holds information about the DVD Content Scrambling System (CSS) feature.
old-location: storage\feature_data_dvd_css.htm
old-project: storage
ms.assetid: 8266f17d-65d6-49a0-a8ea-fee71dff4db0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.feature_data_dvd_css, ntddmmc/PFEATURE_DATA_DVD_CSS, ntddmmc/FEATURE_DATA_DVD_CSS, PFEATURE_DATA_DVD_CSS structure pointer [Storage Devices], FEATURE_DATA_DVD_CSS structure [Storage Devices], _FEATURE_DATA_DVD_CSS, FEATURE_DATA_DVD_CSS, *PFEATURE_DATA_DVD_CSS, structs-CD-ROM_1508ce84-fa86-423e-a6c1-4059bf0cb54c.xml, PFEATURE_DATA_DVD_CSS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddmmc.h
apiname:
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_DVD_CSS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

