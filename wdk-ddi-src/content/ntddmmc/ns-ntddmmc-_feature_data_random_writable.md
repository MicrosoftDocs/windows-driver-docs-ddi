---
UID: NS:ntddmmc._FEATURE_DATA_RANDOM_WRITABLE
title: "_FEATURE_DATA_RANDOM_WRITABLE"
author: windows-driver-content
description: The FEATURE_DATA_RANDOM_WRITABLE structure holds information about the Random Writable feature.
old-location: storage\feature_data_random_writable.htm
old-project: storage
ms.assetid: b2637f5e-15b0-44ae-8cd0-98712e735998
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_RANDOM_WRITABLE, FEATURE_DATA_RANDOM_WRITABLE, FEATURE_DATA_RANDOM_WRITABLE structure [Storage Devices], PFEATURE_DATA_RANDOM_WRITABLE, PFEATURE_DATA_RANDOM_WRITABLE structure pointer [Storage Devices], _FEATURE_DATA_RANDOM_WRITABLE, ntddmmc/FEATURE_DATA_RANDOM_WRITABLE, ntddmmc/PFEATURE_DATA_RANDOM_WRITABLE, storage.feature_data_random_writable, structs-CD-ROM_fa825a20-a941-4af3-aabd-1b9f7e4e3ee6.xml"
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
-	FEATURE_DATA_RANDOM_WRITABLE
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_RANDOM_WRITABLE, *PFEATURE_DATA_RANDOM_WRITABLE
---

# _FEATURE_DATA_RANDOM_WRITABLE structure


## -description


The FEATURE_DATA_RANDOM_WRITABLE structure holds information about the Random Writable feature.


## -syntax


````
typedef struct _FEATURE_DATA_RANDOM_WRITABLE {
  FEATURE_HEADER Header;
  UCHAR          LastLBA[4];
  UCHAR          LogicalBlockSize[4];
  UCHAR          Blocking[2];
  UCHAR          ErrorRecoveryPagePresent  :1;
  UCHAR          Reserved1  :7;
  UCHAR          Reserved2;
} FEATURE_DATA_RANDOM_WRITABLE, *PFEATURE_DATA_RANDOM_WRITABLE;
````


## -struct-fields




### -field Header

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field LastLBA

Contains the logical block address of the last addressable block on the medium. The bytes of this array are arranged in big-endian order. <b>LastLBA</b>[0] contains the most significant byte, and <b>LastLBA</b>[3] contains the least significant byte. 


### -field LogicalBlockSize

Specifies the number of bytes per logical block. The bytes of this array are arranged in big-endian order. <b>LogicalBlockSize</b>[0] contains the most significant byte, and <b>LogicalBlockSize</b>[3] contains the least significant byte. 


### -field Blocking

Indicates the number of logical blocks per device. The bytes of this array are arranged in big-endian order. <b>Blocking</b>[0] contains the most significant byte, and <b>Blocking</b>[1] contains the least significant byte. 


### -field ErrorRecoveryPagePresent

Indicates, when set to zero, that the Read/Write Error Recovery Mode Page might not be present. See the <i>SCSI Multimedia -3 </i>(<i>MMC-3</i>) specification for an explanation of this page. 


### -field Reserved1

Reserved. 


### -field Reserved2

Reserved. 


## -remarks



This structure holds data for the feature named "Random Writable" by the <i>MMC-3 </i>specification. Devices that support this feature can write blocks of data to random locations on the disk. These devices do not require that the initiator address disk locations in any particular order. 




## -see-also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_RANDOM_WRITABLE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

