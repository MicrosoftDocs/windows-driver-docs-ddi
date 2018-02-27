---
UID: NS:ntddmmc._FEATURE_DATA_DVD_CPRM
title: "_FEATURE_DATA_DVD_CPRM"
author: windows-driver-content
description: The FEATURE_DATA_DVD_CPRM structure holds information about the DVD Content Protection for Recorded Media (CPRM) feature.
old-location: storage\feature_data_dvd_cprm.htm
old-project: storage
ms.assetid: 060c1e9a-14d3-4f9b-b898-d8042f5efd7e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PFEATURE_DATA_DVD_CPRM, FEATURE_DATA_DVD_CPRM, FEATURE_DATA_DVD_CPRM structure [Storage Devices], PFEATURE_DATA_DVD_CPRM, PFEATURE_DATA_DVD_CPRM structure pointer [Storage Devices], _FEATURE_DATA_DVD_CPRM, ntddmmc/FEATURE_DATA_DVD_CPRM, ntddmmc/PFEATURE_DATA_DVD_CPRM, storage.feature_data_dvd_cprm, structs-CD-ROM_376d4f99-5d92-48ad-b126-d1f6858e7fac.xml"
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
-	FEATURE_DATA_DVD_CPRM
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_DVD_CPRM, *PFEATURE_DATA_DVD_CPRM
---

# _FEATURE_DATA_DVD_CPRM structure


## -description


The FEATURE_DATA_DVD_CPRM structure holds information about the DVD Content Protection for Recorded Media (CPRM) feature. 


## -syntax


````
typedef struct _FEATURE_DATA_DVD_CPRM {
  FEATURE_HEADER Header;
  UCHAR          Reserved0[3];
  UCHAR          CPRMVersion;
} FEATURE_DATA_DVD_CPRM, *PFEATURE_DATA_DVD_CPRM;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Reserved0

Reserved. 


### -field CPRMVersion

Contains the CPRM version number. Must be set to 1. 


## -remarks



This structure holds data for the feature named "DVD CPRM" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can perform DVD Content Protection for Recordable Media (CPRM) authentication and key management. 




## -see-also

<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_DVD_CPRM structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

