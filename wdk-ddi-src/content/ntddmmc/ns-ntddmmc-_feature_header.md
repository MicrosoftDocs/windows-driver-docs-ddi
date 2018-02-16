---
UID: NS:ntddmmc._FEATURE_HEADER
title: "_FEATURE_HEADER"
author: windows-driver-content
description: The FEATURE_HEADER structure is used in conjunction with the IOCTL_CDROM_GET_CONFIGURATION request to report header information for both feature and profile descriptors.
old-location: storage\feature_header.htm
old-project: storage
ms.assetid: 61831fbb-48ad-4831-8b69-7b1a5cafa629
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: FEATURE_HEADER, FEATURE_HEADER structure [Storage Devices], ntddmmc/FEATURE_HEADER, PFEATURE_HEADER, storage.feature_header, structs-CD-ROM_41d7886f-d383-4416-8f89-b40f1bb0bc7f.xml, PFEATURE_HEADER structure pointer [Storage Devices], ntddmmc/PFEATURE_HEADER, *PFEATURE_HEADER, _FEATURE_HEADER
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
-	FEATURE_HEADER
product: Windows
targetos: Windows
req.typenames: "*PFEATURE_HEADER, FEATURE_HEADER"
---

# _FEATURE_HEADER structure


## -description


The FEATURE_HEADER structure is used in conjunction with the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_configuration.md">IOCTL_CDROM_GET_CONFIGURATION</a> request to report header information for both feature and profile descriptors.


## -syntax


````
typedef struct _FEATURE_HEADER {
  UCHAR FeatureCode[2];
  UCHAR Current  :1;
  UCHAR Persistent  :1;
  UCHAR Version  :4;
  UCHAR Reserved0  :2;
  UCHAR AdditionalLength;
} FEATURE_HEADER, *PFEATURE_HEADER;
````


## -struct-fields




### -field FeatureCode

Contains a value between zero and 0xffff that indicates a feature. The <a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a> enumeration provides a list of currently supported feature numbers. <b>FeatureCode</b>[0] contains the most significant byte of the feature number. <b>FeatureCode</b>[1] contains the least significant byte. 


### -field Current

Indicates, when set to 1, that this feature is currently active and the data reported for the feature is valid. When set to zero, this bit indicates that the feature is not currently active and that the data reported for the feature might not be valid. 


### -field Persistent

Indicates, when set to 1, that the feature is always active. When set to zero, this bit indicates that the feature is not always active. 


### -field Version

Must be set to zero unless otherwise specified within the description for a particular feature.


### -field Reserved0

Reserved.


### -field AdditionalLength

Indicates the number of bytes of feature information that follow this header. This member must be an integral multiple of 4. The total size of the data related to this feature will be <b>AdditionalLength</b> + <b>sizeof</b>(FEATURE_HEADER).


## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_get_configuration_header.md">GET_CONFIGURATION_HEADER</a>



<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_configuration.md">IOCTL_CDROM_GET_CONFIGURATION</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_HEADER structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

