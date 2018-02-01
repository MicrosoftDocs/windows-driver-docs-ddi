---
UID: NS:ntddmmc._FEATURE_DATA_CORE
title: "_FEATURE_DATA_CORE"
author: windows-driver-content
description: The FEATURE_DATA_CORE structure holds data for the Core feature descriptor.
old-location: storage\feature_data_core.htm
old-project: storage
ms.assetid: cd8e989a-1030-4f37-bb39-38974764ccb2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddmmc/PFEATURE_DATA_CORE, ntddmmc/FEATURE_DATA_CORE, FEATURE_DATA_CORE, *PFEATURE_DATA_CORE, structs-CD-ROM_1b2608f2-398d-4733-b319-a92d932504e7.xml, FEATURE_DATA_CORE structure [Storage Devices], _FEATURE_DATA_CORE, PFEATURE_DATA_CORE, PFEATURE_DATA_CORE structure pointer [Storage Devices], storage.feature_data_core
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
-	FEATURE_DATA_CORE
product: Windows
targetos: Windows
req.typenames: "*PFEATURE_DATA_CORE, FEATURE_DATA_CORE"
---

# _FEATURE_DATA_CORE structure


## -description


The FEATURE_DATA_CORE structure holds data for the Core feature descriptor.


## -syntax


````
typedef struct _FEATURE_DATA_CORE {
  FEATURE_HEADER Header;
  UCHAR          PhysicalInterface[4];
  UCHAR          DeviceBusyEvent  :1;
  UCHAR          INQUIRY2  :1;
  UCHAR          Reserved1  :6;
  UCHAR          Reserved2[3];
} FEATURE_DATA_CORE, *PFEATURE_DATA_CORE;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field PhysicalInterface

Must be set to the current communication path between initiator and device, as defined in the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. The bytes of this array are arranged in big-endian order. <b>PhysicalInterface</b>[0] contains the most significant byte, and <b>PhysicalInterface</b>[3] contains the least significant byte.


### -field DeviceBusyEvent



### -field INQUIRY2



### -field Reserved1



### -field Reserved2



## -remarks


Indicates the feature named "Core" by the <i>MMC-3 </i>specification. This feature encompasses the basic functionality which is mandatory for all devices that support the <i>MMC-3</i> standard. See the <i>MMC-3</i> specification for a description of the capabilities included in the Core feature. 



## -see-also

<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_CORE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

