---
UID: NS:ntddmmc._FEATURE_DATA_CDRW_CAV_WRITE
title: "_FEATURE_DATA_CDRW_CAV_WRITE"
author: windows-driver-content
description: The FEATURE_DATA_CDRW_CAV_WRITE structure contains information about the CD-RW CAV Write feature.
old-location: storage\feature_data_cdrw_cav_write.htm
old-project: storage
ms.assetid: bdd76553-d551-4451-8a34-122bc0639665
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_CDRW_CAV_WRITE, FEATURE_DATA_CDRW_CAV_WRITE, FEATURE_DATA_CDRW_CAV_WRITE structure [Storage Devices], PFEATURE_DATA_CDRW_CAV_WRITE, PFEATURE_DATA_CDRW_CAV_WRITE structure pointer [Storage Devices], _FEATURE_DATA_CDRW_CAV_WRITE, ntddmmc/FEATURE_DATA_CDRW_CAV_WRITE, ntddmmc/PFEATURE_DATA_CDRW_CAV_WRITE, storage.feature_data_cdrw_cav_write, structs-CD-ROM_2ebe5ae8-15be-47a8-9bb8-d638f6033e6b.xml"
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
-	FEATURE_DATA_CDRW_CAV_WRITE
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_CDRW_CAV_WRITE, *PFEATURE_DATA_CDRW_CAV_WRITE
---

# _FEATURE_DATA_CDRW_CAV_WRITE structure


## -description


The FEATURE_DATA_CDRW_CAV_WRITE structure contains information about the CD-RW CAV Write feature. 


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Reserved1

Reserved. 


## -remarks



This structure holds data for the feature named "CD-RW CAV Write" by the <i>SCSI Multimedia - 4 (MMC-4) </i>specification. Devices that support this feature can perform writes on CD-RW media in CAV mode. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

