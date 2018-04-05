---
UID: NS:ntddmmc._FEATURE_DATA_DVD_PLUS_RW
title: "_FEATURE_DATA_DVD_PLUS_RW"
author: windows-driver-content
description: The FEATURE_DATA_DVD_PLUS_RW structure contains information about the DVD+RW feature.
old-location: storage\feature_data_dvd_plus_rw.htm
old-project: storage
ms.assetid: 55cbef36-dea7-4f7c-ac43-fb819b61a858
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_DVD_PLUS_RW, FEATURE_DATA_DVD_PLUS_RW, FEATURE_DATA_DVD_PLUS_RW structure [Storage Devices], PFEATURE_DATA_DVD_PLUS_RW, PFEATURE_DATA_DVD_PLUS_RW structure pointer [Storage Devices], _FEATURE_DATA_DVD_PLUS_RW, ntddmmc/FEATURE_DATA_DVD_PLUS_RW, ntddmmc/PFEATURE_DATA_DVD_PLUS_RW, storage.feature_data_dvd_plus_rw, structs-CD-ROM_8b49bf86-5e1a-42a3-9bb6-ba6afca60375.xml"
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
-	FEATURE_DATA_DVD_PLUS_RW
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_DVD_PLUS_RW, *PFEATURE_DATA_DVD_PLUS_RW
---

# _FEATURE_DATA_DVD_PLUS_RW structure


## -description


The FEATURE_DATA_DVD_PLUS_RW structure contains information about the DVD+RW feature. 


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Write

Indicates, when set to 1, that the device can do background formatting of DVD+RW discs according to <i>DVD+RW 4.7 Gbytes Basic Format Specifications</i>, and can write to discs that have been formatted in this manner. 


### -field Reserved1

Reserved. 


### -field CloseOnly

Indicates, when set to 1, then the device supports only read compatibility stops. When set to 0, the device supports both forms of background format stop. For more information about background format stops, see the <i>SCSI Multimedia Commands - 4 (MMC-4)</i> specification published by the American National Standards Institute (ANSI).


### -field QuickStart


### -field Reserved02


### -field Reserved03


## -remarks



This structure holds data for the feature named "DVD+RW" by the <i>SCSI Multimedia - 4 (MMC-4) </i>specification. Devices that support this feature can read a recorded DVD+RW disc that is formatted according to the <i>DVD+RW 4.7 Gbytes Basic Format Specification. </i>




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

