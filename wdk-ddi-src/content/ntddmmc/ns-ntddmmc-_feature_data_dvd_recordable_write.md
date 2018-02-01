---
UID: NS:ntddmmc._FEATURE_DATA_DVD_RECORDABLE_WRITE
title: "_FEATURE_DATA_DVD_RECORDABLE_WRITE"
author: windows-driver-content
description: The FEATURE_DATA_DVD_RECORDABLE_WRITE structure holds information for the DVD-R/RW Write feature.
old-location: storage\feature_data_dvd_recordable_write.htm
old-project: storage
ms.assetid: 13a816f9-c41a-49f1-ac79-98106f4630d4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: FEATURE_DATA_DVD_RECORDABLE_WRITE, ntddmmc/PFEATURE_DATA_DVD_RECORDABLE_WRITE, PFEATURE_DATA_DVD_RECORDABLE_WRITE structure pointer [Storage Devices], FEATURE_DATA_DVD_RECORDABLE_WRITE structure [Storage Devices], _FEATURE_DATA_DVD_RECORDABLE_WRITE, *PFEATURE_DATA_DVD_RECORDABLE_WRITE, ntddmmc/FEATURE_DATA_DVD_RECORDABLE_WRITE, structs-CD-ROM_c7d92388-964e-4db2-803a-1a7c10c45cc0.xml, PFEATURE_DATA_DVD_RECORDABLE_WRITE, storage.feature_data_dvd_recordable_write
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
-	FEATURE_DATA_DVD_RECORDABLE_WRITE
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_DVD_RECORDABLE_WRITE, *PFEATURE_DATA_DVD_RECORDABLE_WRITE
---

# _FEATURE_DATA_DVD_RECORDABLE_WRITE structure


## -description


The FEATURE_DATA_DVD_RECORDABLE_WRITE structure holds information for the DVD-R/RW Write feature.


## -syntax


````
typedef struct _FEATURE_DATA_DVD_RECORDABLE_WRITE {
  FEATURE_HEADER Header;
  UCHAR          Reserved1  :1;
  UCHAR          DVD_RW  :1;
  UCHAR          TestWrite  :1;
  UCHAR          RDualLayer  :1;
  UCHAR          Reserved02  :2;
  UCHAR          BufferUnderrunFree  :1;
  UCHAR          Reserved3  :1;
  UCHAR          Reserved4[3];
} FEATURE_DATA_DVD_RECORDABLE_WRITE, *PFEATURE_DATA_DVD_RECORDABLE_WRITE;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Reserved1

Reserved. 


### -field DVD_RW

Indicates, when set to 1, that the device supports writing and erasing on DVD-RW media. For more information about this feature see the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. 


### -field TestWrite

Indicates, when set to 1, that the device is capable of performing test writes. When set to zero, the device cannot perform test writes. 


### -field RDualLayer



### -field Reserved02



### -field BufferUnderrunFree

Indicates, when set to 1, that the device can perform under-run-free recording. 


### -field Reserved3

Reserved. 


### -field Reserved4

Reserved. 


## -remarks


This structure holds data for the feature named "DVD-R Write" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can write data to a write-once DVD media in "Disc-at-Once" mode.



## -see-also

<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_DVD_RECORDABLE_WRITE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

