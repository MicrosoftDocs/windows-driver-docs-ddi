---
UID: NS:ntddmmc._FEATURE_DATA_TIMEOUT
title: "_FEATURE_DATA_TIMEOUT"
author: windows-driver-content
description: The FEATURE_DATA_TIMEOUT structure holds information about the Time-Out feature.
old-location: storage\feature_data_timeout.htm
old-project: storage
ms.assetid: 0699dcc3-ab43-436e-b7d3-09898e4d823c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: FEATURE_DATA_TIMEOUT, PFEATURE_DATA_TIMEOUT structure pointer [Storage Devices], ntddmmc/FEATURE_DATA_TIMEOUT, *PFEATURE_DATA_TIMEOUT, ntddmmc/PFEATURE_DATA_TIMEOUT, storage.feature_data_timeout, structs-CD-ROM_2de49c50-b26e-42c0-b637-40f752b59891.xml, _FEATURE_DATA_TIMEOUT, FEATURE_DATA_TIMEOUT structure [Storage Devices], PFEATURE_DATA_TIMEOUT
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
-	FEATURE_DATA_TIMEOUT
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_TIMEOUT, *PFEATURE_DATA_TIMEOUT
---

# _FEATURE_DATA_TIMEOUT structure


## -description


The FEATURE_DATA_TIMEOUT structure holds information about the Time-Out feature.


## -syntax


````
typedef struct _FEATURE_DATA_TIMEOUT {
  FEATURE_HEADER Header;
  UCHAR          Group3  :1;
  UCHAR          Reserved1  :7;
  UCHAR          Reserved2;
  UCHAR          UnitLength[2];
} FEATURE_DATA_TIMEOUT, *PFEATURE_DATA_TIMEOUT;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.


### -field Group3


### -field Reserved1


### -field Reserved2


### -field UnitLength


## -remarks



This structure holds data for the feature named "Time-Out" by the <i>SCSI Multimedia - 4 (MMC-4) </i>specification. Devices that have this feature must respond to commands within a set time period. When these devices cannot complete commands in the allotted time, they complete the commands with an error.

When queried, devices supporting this feature must return the information indicated in <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>. No other feature-specific information is required. 




## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_TIMEOUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

