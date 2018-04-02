---
UID: NS:ntddmmc._FEATURE_DATA_DVD_READ
title: "_FEATURE_DATA_DVD_READ"
author: windows-driver-content
description: The FEATURE_DATA_DVD_READ structure contains information about the DVD Read feature.
old-location: storage\feature_data_dvd_read.htm
old-project: storage
ms.assetid: 489d3edc-4966-481e-b5c8-6979173e9341
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_DVD_READ, FEATURE_DATA_DVD_READ, FEATURE_DATA_DVD_READ structure [Storage Devices], PFEATURE_DATA_DVD_READ, PFEATURE_DATA_DVD_READ structure pointer [Storage Devices], _FEATURE_DATA_DVD_READ, ntddmmc/FEATURE_DATA_DVD_READ, ntddmmc/PFEATURE_DATA_DVD_READ, storage.feature_data_dvd_read, structs-CD-ROM_94af17d0-72ec-4248-9035-4050f6e3c275.xml"
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
-	FEATURE_DATA_DVD_READ
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_DVD_READ, *PFEATURE_DATA_DVD_READ
---

# _FEATURE_DATA_DVD_READ structure


## -description


The FEATURE_DATA_DVD_READ structure contains information about the DVD Read feature.


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Multi110


### -field Reserved1


### -field Reserved2


### -field DualDashR


### -field Reserved3


### -field Reserved4


## -remarks



This structure holds data for the feature named "DVD Read" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can read DVD-specific information from the media.

When queried, devices supporting this feature must return the information indicated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>. No other feature-specific information is required. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

