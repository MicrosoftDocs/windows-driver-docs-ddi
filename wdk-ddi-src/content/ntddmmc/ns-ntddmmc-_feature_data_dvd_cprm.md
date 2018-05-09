---
UID: NS:ntddmmc._FEATURE_DATA_DVD_CPRM
title: "_FEATURE_DATA_DVD_CPRM"
author: windows-driver-content
description: The FEATURE_DATA_DVD_CPRM structure holds information about the DVD Content Protection for Recorded Media (CPRM) feature.
old-location: storage\feature_data_dvd_cprm.htm
old-project: storage
ms.assetid: 060c1e9a-14d3-4f9b-b898-d8042f5efd7e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_DVD_CPRM, FEATURE_DATA_DVD_CPRM, FEATURE_DATA_DVD_CPRM structure [Storage Devices], PFEATURE_DATA_DVD_CPRM, PFEATURE_DATA_DVD_CPRM structure pointer [Storage Devices], _FEATURE_DATA_DVD_CPRM, ntddmmc/FEATURE_DATA_DVD_CPRM, ntddmmc/PFEATURE_DATA_DVD_CPRM, storage.feature_data_dvd_cprm, structs-CD-ROM_376d4f99-5d92-48ad-b126-d1f6858e7fac.xml"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddmmc.h
api_name:
-	FEATURE_DATA_DVD_CPRM
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_DVD_CPRM, *PFEATURE_DATA_DVD_CPRM
---

# _FEATURE_DATA_DVD_CPRM structure


## -description


The FEATURE_DATA_DVD_CPRM structure holds information about the DVD Content Protection for Recorded Media (CPRM) feature. 


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Reserved0

Reserved. 


### -field CPRMVersion

Contains the CPRM version number. Must be set to 1. 


## -remarks



This structure holds data for the feature named "DVD CPRM" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can perform DVD Content Protection for Recordable Media (CPRM) authentication and key management. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

