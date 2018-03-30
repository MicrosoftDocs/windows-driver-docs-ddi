---
UID: NS:ntddmmc._FEATURE_DATA_WRITE_ONCE
title: "_FEATURE_DATA_WRITE_ONCE"
author: windows-driver-content
description: The FEATURE_DATA_WRITE_ONCE structure holds information for the Write Once feature.
old-location: storage\feature_data_write_once.htm
old-project: storage
ms.assetid: d8352a73-6b3e-4890-a4ae-000d453d1143
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_WRITE_ONCE, FEATURE_DATA_WRITE_ONCE, FEATURE_DATA_WRITE_ONCE structure [Storage Devices], PFEATURE_DATA_WRITE_ONCE, PFEATURE_DATA_WRITE_ONCE structure pointer [Storage Devices], _FEATURE_DATA_WRITE_ONCE, ntddmmc/FEATURE_DATA_WRITE_ONCE, ntddmmc/PFEATURE_DATA_WRITE_ONCE, storage.feature_data_write_once, structs-CD-ROM_d10e83bf-73ef-43e2-901f-20ca3edea1ac.xml"
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
-	FEATURE_DATA_WRITE_ONCE
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_WRITE_ONCE, *PFEATURE_DATA_WRITE_ONCE
---

# _FEATURE_DATA_WRITE_ONCE structure


## -description


The FEATURE_DATA_WRITE_ONCE structure holds information for the Write Once feature.


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

