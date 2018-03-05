---
UID: NS:ntddmmc._FEATURE_DATA_CD_READ
title: "_FEATURE_DATA_CD_READ"
author: windows-driver-content
description: The FEATURE_DATA_CD_READ structure contains information about the CD Read feature.
old-location: storage\feature_data_cd_read.htm
old-project: storage
ms.assetid: 55d63dcc-7728-4982-ad1c-e1ca40cc941e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_CD_READ, FEATURE_DATA_CD_READ, FEATURE_DATA_CD_READ structure [Storage Devices], PFEATURE_DATA_CD_READ, PFEATURE_DATA_CD_READ structure pointer [Storage Devices], _FEATURE_DATA_CD_READ, ntddmmc/FEATURE_DATA_CD_READ, ntddmmc/PFEATURE_DATA_CD_READ, storage.feature_data_cd_read, structs-CD-ROM_8b31a56d-f370-4b85-8f37-a88041276a20.xml"
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
-	FEATURE_DATA_CD_READ
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_CD_READ, *PFEATURE_DATA_CD_READ
---

# _FEATURE_DATA_CD_READ structure


## -description


The FEATURE_DATA_CD_READ structure contains information about the CD Read feature.


## -syntax


````
typedef struct _FEATURE_DATA_CD_READ {
  FEATURE_HEADER Header;
  UCHAR          CDText  :1;
  UCHAR          C2ErrorData  :1;
  UCHAR          Reserved01  :5;
  UCHAR          DigitalAudioPlay  :1;
  UCHAR          Reserved2[3];
} FEATURE_DATA_CD_READ, *PFEATURE_DATA_CD_READ;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field CDText

Indicates, when set to 1, that the device supports format code 0x05 of the READ/TOC/PMA/ATIP command, as defined in the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. When set to zero, CD-Text is not supported. 


### -field C2ErrorData

Indicates, when set to 1, that the device supports the C2 error pointers as described in the <i>MMC-3 </i>specification. When set to zero, it indicates that the device does not support C2 error pointers.


### -field Reserved01


### -field DigitalAudioPlay


### -field Reserved2

Reserved. 


## -remarks



This structure holds data for the feature named "CD Read" by the <i>MMC-3 </i>specification. Devices that support this feature can read CD-specific information from the media and can read user data from all types of CD blocks. 




## -see-also

<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_CD_READ structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

