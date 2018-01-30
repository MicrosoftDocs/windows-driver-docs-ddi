---
UID: NS:ntddmmc._FEATURE_DATA_SMART
title: "_FEATURE_DATA_SMART"
author: windows-driver-content
description: The FEATURE_DATA_SMART structure holds data for the S.M.A.R.T. feature.
old-location: storage\feature_data_smart.htm
old-project: storage
ms.assetid: cf6578d1-e455-4bbe-a89f-bc0292e24a4a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "_FEATURE_DATA_SMART, PFEATURE_DATA_SMART, ntddmmc/FEATURE_DATA_SMART, structs-CD-ROM_3d912360-2734-4d01-b7ef-298d90be28b7.xml, ntddmmc/PFEATURE_DATA_SMART, FEATURE_DATA_SMART structure [Storage Devices], *PFEATURE_DATA_SMART, FEATURE_DATA_SMART, storage.feature_data_smart, PFEATURE_DATA_SMART structure pointer [Storage Devices]"
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
-	FEATURE_DATA_SMART
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_SMART, *PFEATURE_DATA_SMART
---

# _FEATURE_DATA_SMART structure


## -description


The FEATURE_DATA_SMART structure holds data for the S.M.A.R.T. feature.


## -syntax


````
typedef struct _FEATURE_DATA_SMART {
  FEATURE_HEADER Header;
  UCHAR          FaultFailureReportingPagePresent  :1;
  UCHAR          Reserved1  :7;
  UCHAR          Reserved02[3];
} FEATURE_DATA_SMART, *PFEATURE_DATA_SMART;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.


### -field FaultFailureReportingPagePresent

Indicates, when set to 1, that the device supports the Fault / Failure Reporting Mode. If set to zero, the device does not support this mode. 


### -field Reserved1

Reserved.


### -field Reserved02

Reserved.


## -remarks


This structure holds data for the feature named "S.M.A.R.T." by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature support Self-Monitoring Analysis and Reporting Technology (SMART).



## -see-also

<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_SMART structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

