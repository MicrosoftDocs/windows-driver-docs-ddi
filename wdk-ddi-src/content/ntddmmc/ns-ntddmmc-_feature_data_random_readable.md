---
UID: NS:ntddmmc._FEATURE_DATA_RANDOM_READABLE
title: _FEATURE_DATA_RANDOM_READABLE (ntddmmc.h)
description: The FEATURE_DATA_RANDOM_READABLE structure contains data for the random readable feature.
old-location: storage\feature_data_random_readable.htm
tech.root: storage
ms.assetid: c235a3aa-f8fe-4034-a645-ef85b2574fa0
ms.date: 03/29/2018
ms.keywords: "*PFEATURE_DATA_RANDOM_READABLE, FEATURE_DATA_RANDOM_READABLE, FEATURE_DATA_RANDOM_READABLE structure [Storage Devices], PFEATURE_DATA_RANDOM_READABLE, PFEATURE_DATA_RANDOM_READABLE structure pointer [Storage Devices], _FEATURE_DATA_RANDOM_READABLE, ntddmmc/FEATURE_DATA_RANDOM_READABLE, ntddmmc/PFEATURE_DATA_RANDOM_READABLE, storage.feature_data_random_readable, structs-CD-ROM_90540677-8abb-43d0-919a-821411398074.xml"
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
-	FEATURE_DATA_RANDOM_READABLE
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_RANDOM_READABLE, *PFEATURE_DATA_RANDOM_READABLE
---

# _FEATURE_DATA_RANDOM_READABLE structure


## -description


The FEATURE_DATA_RANDOM_READABLE structure contains data for the random readable feature. 


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field LogicalBlockSize

Indicates the number of bytes per logical block. The bytes of this value are arranged in big-endian order. <b>LogicalBlockSize</b>[0] contains the most significant byte, and <b>LogicalBlockSize</b>[3] contains the least significant byte.


### -field Blocking

Indicates the number of logical blocks per device-readable unit. The bytes of this value are arranged in big-endian order. <b>Blocking</b>[0] contains the most significant byte, and <b>Blocking</b>[1] contains the least significant byte. 


### -field ErrorRecoveryPagePresent

Indicates, when set to zero, that the read/write error recovery mode page might not be present. When set to 1, it indicates that the error recovery page is present. 


### -field Reserved1

Reserved. 


### -field Reserved2

Reserved. 


## -remarks



This structure holds data for the feature named "Random Readable" by the <i>MMC-3 </i>specification. Devices that support this feature allow the initiator to read blocks of data on the disk at random locations. These devices do not require that the initiator address disk locations in any particular order. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

