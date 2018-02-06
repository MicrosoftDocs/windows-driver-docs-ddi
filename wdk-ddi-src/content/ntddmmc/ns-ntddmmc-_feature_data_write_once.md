---
UID: NS:ntddmmc._FEATURE_DATA_WRITE_ONCE
title: "_FEATURE_DATA_WRITE_ONCE"
author: windows-driver-content
description: The FEATURE_DATA_WRITE_ONCE structure holds information for the Write Once feature.
old-location: storage\feature_data_write_once.htm
old-project: storage
ms.assetid: d8352a73-6b3e-4890-a4ae-000d453d1143
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: structs-CD-ROM_d10e83bf-73ef-43e2-901f-20ca3edea1ac.xml, FEATURE_DATA_WRITE_ONCE, PFEATURE_DATA_WRITE_ONCE structure pointer [Storage Devices], FEATURE_DATA_WRITE_ONCE structure [Storage Devices], PFEATURE_DATA_WRITE_ONCE, *PFEATURE_DATA_WRITE_ONCE, ntddmmc/PFEATURE_DATA_WRITE_ONCE, ntddmmc/FEATURE_DATA_WRITE_ONCE, _FEATURE_DATA_WRITE_ONCE, storage.feature_data_write_once
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
-	FEATURE_DATA_WRITE_ONCE
product: Windows
targetos: Windows
req.typenames: "*PFEATURE_DATA_WRITE_ONCE, FEATURE_DATA_WRITE_ONCE"
---

# _FEATURE_DATA_WRITE_ONCE structure


## -description


The FEATURE_DATA_WRITE_ONCE structure holds information for the Write Once feature.


## -syntax


````
typedef struct _FEATURE_DATA_WRITE_ONCE {
  FEATURE_HEADER Header;
  UCHAR          LogicalBlockSize[4];
  UCHAR          Blocking[2];
  UCHAR          ErrorRecoveryPagePresent  :1;
  UCHAR          Reserved1  :7;
  UCHAR          Reserved2;
} FEATURE_DATA_WRITE_ONCE, *PFEATURE_DATA_WRITE_ONCE;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field LogicalBlockSize

Indicates the number of bytes per logical block. The bytes in this array are arranged in big-endian order. <b>LogicalBlockSize</b>[0] holds the most significant byte. <b>LogicalBlockSize</b>[3] holds the least significant byte. 


### -field Blocking

Indicates the number of logical blocks per device. The bytes in this array are arranged in big-endian order. <b>Blocking</b>[0] holds the most significant byte. <b>Blocking</b>[1] holds the least significant byte. 


### -field ErrorRecoveryPagePresent

Indicates, when set to 1, that the Read/Write Error Recovery Mode Page is present. When set to zero, indicates that it might not be present. See the <i>SCSI Multimedia 3</i> (<i>MMC-3</i>) specification for a description of this page. 


### -field Reserved1

Reserved. 


### -field Reserved2

Reserved. 


## -remarks


This structure holds data for the feature named "Write Once" by the <i>MMC-3 </i>specification. Devices that support this feature can write to any previously unused logical block. 



## -see-also

<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_WRITE_ONCE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

