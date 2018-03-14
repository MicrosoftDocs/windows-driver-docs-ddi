---
UID: NS:ntddmmc._FEATURE_DATA_DVD_PLUS_RW
title: "_FEATURE_DATA_DVD_PLUS_RW"
author: windows-driver-content
description: The FEATURE_DATA_DVD_PLUS_RW structure contains information about the DVD+RW feature.
old-location: storage\feature_data_dvd_plus_rw.htm
old-project: storage
ms.assetid: 55cbef36-dea7-4f7c-ac43-fb819b61a858
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_DVD_PLUS_RW, FEATURE_DATA_DVD_PLUS_RW, FEATURE_DATA_DVD_PLUS_RW structure [Storage Devices], PFEATURE_DATA_DVD_PLUS_RW, PFEATURE_DATA_DVD_PLUS_RW structure pointer [Storage Devices], _FEATURE_DATA_DVD_PLUS_RW, ntddmmc/FEATURE_DATA_DVD_PLUS_RW, ntddmmc/PFEATURE_DATA_DVD_PLUS_RW, storage.feature_data_dvd_plus_rw, structs-CD-ROM_8b49bf86-5e1a-42a3-9bb6-ba6afca60375.xml"
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
-	FEATURE_DATA_DVD_PLUS_RW
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_DVD_PLUS_RW, *PFEATURE_DATA_DVD_PLUS_RW
---

# _FEATURE_DATA_DVD_PLUS_RW structure


## -description


The FEATURE_DATA_DVD_PLUS_RW structure contains information about the DVD+RW feature. 


## -syntax


````
typedef struct _FEATURE_DATA_DVD_PLUS_RW {
  FEATURE_HEADER Header;
  UCHAR          Write  :1;
  UCHAR          Reserved1  :7;
  UCHAR          CloseOnly  :1;
  UCHAR          QuickStart  :1;
  UCHAR          Reserved02  :6;
  UCHAR          Reserved03[2];
} FEATURE_DATA_DVD_PLUS_RW, *PFEATURE_DATA_DVD_PLUS_RW;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Write

Indicates, when set to 1, that the device can do background formatting of DVD+RW discs according to <i>DVD+RW 4.7 Gbytes Basic Format Specifications</i>, and can write to discs that have been formatted in this manner. 


### -field Reserved1

Reserved. 


### -field CloseOnly

Indicates, when set to 1, then the device supports only read compatibility stops. When set to 0, the device supports both forms of background format stop. For more information about background format stops, see the <i>SCSI Multimedia Commands - 4 (MMC-4)</i> specification published by the American National Standards Institute (ANSI).


### -field QuickStart


### -field Reserved02


### -field Reserved03


## -remarks



This structure holds data for the feature named "DVD+RW" by the <i>SCSI Multimedia - 4 (MMC-4) </i>specification. Devices that support this feature can read a recorded DVD+RW disc that is formatted according to the <i>DVD+RW 4.7 Gbytes Basic Format Specification. </i>




## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_DVD_PLUS_RW structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

