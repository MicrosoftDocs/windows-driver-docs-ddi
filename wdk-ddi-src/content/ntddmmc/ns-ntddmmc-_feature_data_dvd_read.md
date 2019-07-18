---
UID: NS:ntddmmc._FEATURE_DATA_DVD_READ
title: _FEATURE_DATA_DVD_READ (ntddmmc.h)
description: The FEATURE_DATA_DVD_READ structure contains information about the DVD Read feature.
old-location: storage\feature_data_dvd_read.htm
tech.root: storage
ms.assetid: 489d3edc-4966-481e-b5c8-6979173e9341
ms.date: 03/29/2018
ms.keywords: "*PFEATURE_DATA_DVD_READ, FEATURE_DATA_DVD_READ, FEATURE_DATA_DVD_READ structure [Storage Devices], PFEATURE_DATA_DVD_READ, PFEATURE_DATA_DVD_READ structure pointer [Storage Devices], _FEATURE_DATA_DVD_READ, ntddmmc/FEATURE_DATA_DVD_READ, ntddmmc/PFEATURE_DATA_DVD_READ, storage.feature_data_dvd_read, structs-CD-ROM_94af17d0-72ec-4248-9035-4050f6e3c275.xml"
ms.topic: struct
f1_keywords:
 - "ntddmmc/FEATURE_DATA_DVD_READ"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddmmc.h
api_name:
- FEATURE_DATA_DVD_READ
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

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Multi110


### -field Reserved1


### -field Reserved2


### -field DualDashR


### -field Reserved3


### -field Reserved4


## -remarks



This structure holds data for the feature named "DVD Read" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can read DVD-specific information from the media.

When queried, devices supporting this feature must return the information indicated in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>. No other feature-specific information is required. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>
 

 

