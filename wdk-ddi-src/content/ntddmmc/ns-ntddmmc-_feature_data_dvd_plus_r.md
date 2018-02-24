---
UID: NS:ntddmmc._FEATURE_DATA_DVD_PLUS_R
title: "_FEATURE_DATA_DVD_PLUS_R"
author: windows-driver-content
description: The FEATURE_DATA_DVD_PLUS_R structure contains information about the DVD+R feature.
old-location: storage\feature_data_dvd_plus_r.htm
old-project: storage
ms.assetid: e1501ea9-a55b-4fbc-990b-2172c7369bb1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FEATURE_DATA_DVD_PLUS_R structure [Storage Devices], _FEATURE_DATA_DVD_PLUS_R, ntddmmc/PFEATURE_DATA_DVD_PLUS_R, FEATURE_DATA_DVD_PLUS_R, PFEATURE_DATA_DVD_PLUS_R, PFEATURE_DATA_DVD_PLUS_R structure pointer [Storage Devices], structs-CD-ROM_fb4a1383-3c8f-48e8-8fc8-3796e00f80a6.xml, ntddmmc/FEATURE_DATA_DVD_PLUS_R, storage.feature_data_dvd_plus_r, *PFEATURE_DATA_DVD_PLUS_R
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
-	FEATURE_DATA_DVD_PLUS_R
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_DVD_PLUS_R, *PFEATURE_DATA_DVD_PLUS_R
---

# _FEATURE_DATA_DVD_PLUS_R structure


## -description


The FEATURE_DATA_DVD_PLUS_R structure contains information about the DVD+R feature. 


## -syntax


````
typedef struct _FEATURE_DATA_DVD_PLUS_R {
  FEATURE_HEADER Header;
  UCHAR          Write  :1;
  UCHAR          Reserved1  :7;
  UCHAR          Reserved2[3];
} FEATURE_DATA_DVD_PLUS_R, *PFEATURE_DATA_DVD_PLUS_R;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Write

Indicates, when set to 1, that the device has an ability that was not specified in the DVD-ROM profile, to write to DVD+R discs according to <i>DVD+R 4.7 Gbytes Basic Format Specifications.</i> When set to 0, the device has no extra ability beyond what is specified in the profile. 


### -field Reserved1

Reserved. 


### -field Reserved2

Reserved. 


## -remarks



This structure holds data for the feature named "DVD+R" by the <i>MMC-3 </i>specification. Devices that support this feature can specify whether they are able to perform writes to DVD+R discs, even though this ability was not indicated in the device's DVD-ROM profile.




## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_DVD_PLUS_R structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

