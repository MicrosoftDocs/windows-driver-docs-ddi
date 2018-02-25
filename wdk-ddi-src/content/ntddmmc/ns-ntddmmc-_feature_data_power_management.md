---
UID: NS:ntddmmc._FEATURE_DATA_POWER_MANAGEMENT
title: "_FEATURE_DATA_POWER_MANAGEMENT"
author: windows-driver-content
description: The FEATURE_DATA_POWER_MANAGEMENT structure holds information about the Power Management feature.
old-location: storage\feature_data_power_management.htm
old-project: storage
ms.assetid: 0b3f23d1-1081-4fb9-86af-6dbf7bfeb3b7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PFEATURE_DATA_POWER_MANAGEMENT, ,, A, D, E, F, FEATURE_DATA_POWER_MANAGEMENT, FEATURE_DATA_POWER_MANAGEMENT structure [Storage Devices], G, M, N, O, P, PFEATURE_DATA_POWER_MANAGEMENT, PFEATURE_DATA_POWER_MANAGEMENT structure pointer [Storage Devices], R, T, U, W, _, _FEATURE_DATA_POWER_MANAGEMENT, ntddmmc/FEATURE_DATA_POWER_MANAGEMENT, ntddmmc/PFEATURE_DATA_POWER_MANAGEMENT, storage.feature_data_power_management, structs-CD-ROM_b2dfa21c-3dd3-40fd-9605-05c36c4b9fc8.xml"
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
-	FEATURE_DATA_POWER_MANAGEMENT
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_POWER_MANAGEMENT, *PFEATURE_DATA_POWER_MANAGEMENT
---

# _FEATURE_DATA_POWER_MANAGEMENT structure


## -description


The FEATURE_DATA_POWER_MANAGEMENT structure holds information about the Power Management feature.


## -syntax


````
typedef struct _FEATURE_DATA_POWER_MANAGEMENT {
  FEATURE_HEADER Header;
} FEATURE_DATA_POWER_MANAGEMENT, *PFEATURE_DATA_POWER_MANAGEMENT;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


## -remarks



This structure holds data for the feature named "Power Management" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can perform both initiator and logical-unit directed power management.

When queried, devices supporting this feature must return the information indicated in <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>. No other feature-specific information is required. 




## -see-also

<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_POWER_MANAGEMENT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

