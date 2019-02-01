---
UID: NS:ntddmmc._FEATURE_DATA_TIMEOUT
title: _FEATURE_DATA_TIMEOUT (ntddmmc.h)
description: The FEATURE_DATA_TIMEOUT structure holds information about the Time-Out feature.
old-location: storage\feature_data_timeout.htm
tech.root: storage
ms.assetid: 0699dcc3-ab43-436e-b7d3-09898e4d823c
ms.date: 03/29/2018
ms.keywords: "*PFEATURE_DATA_TIMEOUT, FEATURE_DATA_TIMEOUT, FEATURE_DATA_TIMEOUT structure [Storage Devices], PFEATURE_DATA_TIMEOUT, PFEATURE_DATA_TIMEOUT structure pointer [Storage Devices], _FEATURE_DATA_TIMEOUT, ntddmmc/FEATURE_DATA_TIMEOUT, ntddmmc/PFEATURE_DATA_TIMEOUT, storage.feature_data_timeout, structs-CD-ROM_2de49c50-b26e-42c0-b637-40f752b59891.xml"
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
-	FEATURE_DATA_TIMEOUT
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_TIMEOUT, *PFEATURE_DATA_TIMEOUT
---

# _FEATURE_DATA_TIMEOUT structure


## -description


The FEATURE_DATA_TIMEOUT structure holds information about the Time-Out feature.


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor.


### -field Group3


### -field Reserved1


### -field Reserved2


### -field UnitLength


## -remarks



This structure holds data for the feature named "Time-Out" by the <i>SCSI Multimedia - 4 (MMC-4) </i>specification. Devices that have this feature must respond to commands within a set time period. When these devices cannot complete commands in the allotted time, they complete the commands with an error.

When queried, devices supporting this feature must return the information indicated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>. No other feature-specific information is required. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

