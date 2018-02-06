---
UID: NS:ntddmmc._FEATURE_DATA_MICROCODE_UPDATE
title: "_FEATURE_DATA_MICROCODE_UPDATE"
author: windows-driver-content
description: The FEATURE_DATA_MICROCODE_UPDATE structure holds information about the Microcode Upgrade feature.
old-location: storage\feature_data_microcode_update.htm
old-project: storage
ms.assetid: ff9f959b-6901-43b8-b335-c0286136b747
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PFEATURE_DATA_MICROCODE_UPDATE, ntddmmc/FEATURE_DATA_MICROCODE_UPDATE, PFEATURE_DATA_MICROCODE_UPDATE, PFEATURE_DATA_MICROCODE_UPDATE structure pointer [Storage Devices], structs-CD-ROM_e2dbda29-d727-4736-93bd-0e115b9d7948.xml, ntddmmc/PFEATURE_DATA_MICROCODE_UPDATE, _FEATURE_DATA_MICROCODE_UPDATE, FEATURE_DATA_MICROCODE_UPDATE, FEATURE_DATA_MICROCODE_UPDATE structure [Storage Devices], storage.feature_data_microcode_update"
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
-	FEATURE_DATA_MICROCODE_UPDATE
product: Windows
targetos: Windows
req.typenames: "*PFEATURE_DATA_MICROCODE_UPDATE, FEATURE_DATA_MICROCODE_UPDATE"
---

# _FEATURE_DATA_MICROCODE_UPDATE structure


## -description


The FEATURE_DATA_MICROCODE_UPDATE structure holds information about the Microcode Upgrade feature.


## -syntax


````
typedef struct _FEATURE_DATA_MICROCODE_UPDATE {
  FEATURE_HEADER Header;
  UCHAR          M5  :1;
  UCHAR          Reserved1  :7;
  UCHAR          Reserved2[3];
} FEATURE_DATA_MICROCODE_UPDATE, *PFEATURE_DATA_MICROCODE_UPDATE;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field M5



### -field Reserved1



### -field Reserved2



## -remarks


This structure holds data for the feature named "Microcode Upgrade" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can upgrade their internal microcode by means of a published interface. 

When queried, devices supporting this feature must return the information indicated in <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>. No other feature-specific information is required. 



## -see-also

<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_MICROCODE_UPDATE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

