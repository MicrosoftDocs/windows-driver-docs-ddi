---
UID: NS:ntddmmc._FEATURE_DATA_DVD_RECORDABLE_WRITE
title: "_FEATURE_DATA_DVD_RECORDABLE_WRITE"
author: windows-driver-content
description: The FEATURE_DATA_DVD_RECORDABLE_WRITE structure holds information for the DVD-R/RW Write feature.
old-location: storage\feature_data_dvd_recordable_write.htm
tech.root: storage
ms.assetid: 13a816f9-c41a-49f1-ac79-98106f4630d4
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_DVD_RECORDABLE_WRITE, FEATURE_DATA_DVD_RECORDABLE_WRITE, FEATURE_DATA_DVD_RECORDABLE_WRITE structure [Storage Devices], PFEATURE_DATA_DVD_RECORDABLE_WRITE, PFEATURE_DATA_DVD_RECORDABLE_WRITE structure pointer [Storage Devices], _FEATURE_DATA_DVD_RECORDABLE_WRITE, ntddmmc/FEATURE_DATA_DVD_RECORDABLE_WRITE, ntddmmc/PFEATURE_DATA_DVD_RECORDABLE_WRITE, storage.feature_data_dvd_recordable_write, structs-CD-ROM_c7d92388-964e-4db2-803a-1a7c10c45cc0.xml"
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
-	FEATURE_DATA_DVD_RECORDABLE_WRITE
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_DVD_RECORDABLE_WRITE, *PFEATURE_DATA_DVD_RECORDABLE_WRITE
---

# _FEATURE_DATA_DVD_RECORDABLE_WRITE structure


## -description


The FEATURE_DATA_DVD_RECORDABLE_WRITE structure holds information for the DVD-R/RW Write feature.


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

