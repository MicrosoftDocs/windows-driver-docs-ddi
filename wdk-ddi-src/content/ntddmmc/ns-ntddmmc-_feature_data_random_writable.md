---
UID: NS:ntddmmc._FEATURE_DATA_RANDOM_WRITABLE
title: "_FEATURE_DATA_RANDOM_WRITABLE" (ntddmmc.h)
description: The FEATURE_DATA_RANDOM_WRITABLE structure holds information about the Random Writable feature.
old-location: storage\feature_data_random_writable.htm
tech.root: storage
ms.assetid: b2637f5e-15b0-44ae-8cd0-98712e735998
ms.date: 03/29/2018
ms.keywords: "*PFEATURE_DATA_RANDOM_WRITABLE, FEATURE_DATA_RANDOM_WRITABLE, FEATURE_DATA_RANDOM_WRITABLE structure [Storage Devices], PFEATURE_DATA_RANDOM_WRITABLE, PFEATURE_DATA_RANDOM_WRITABLE structure pointer [Storage Devices], _FEATURE_DATA_RANDOM_WRITABLE, ntddmmc/FEATURE_DATA_RANDOM_WRITABLE, ntddmmc/PFEATURE_DATA_RANDOM_WRITABLE, storage.feature_data_random_writable, structs-CD-ROM_fa825a20-a941-4af3-aabd-1b9f7e4e3ee6.xml"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddmmc.h
api_name:
-	FEATURE_DATA_RANDOM_WRITABLE
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_RANDOM_WRITABLE, *PFEATURE_DATA_RANDOM_WRITABLE
---

# _FEATURE_DATA_RANDOM_WRITABLE structure


## -description


The FEATURE_DATA_RANDOM_WRITABLE structure holds information about the Random Writable feature.


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

