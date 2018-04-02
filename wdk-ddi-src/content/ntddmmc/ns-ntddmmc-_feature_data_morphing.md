---
UID: NS:ntddmmc._FEATURE_DATA_MORPHING
title: "_FEATURE_DATA_MORPHING"
author: windows-driver-content
description: The FEATURE_DATA_MORPHING structure contains information about the morphing feature.
old-location: storage\feature_data_morphing.htm
old-project: storage
ms.assetid: b3eaabdf-0163-4679-9b22-d8ec53abed59
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_MORPHING, FEATURE_DATA_MORPHING, FEATURE_DATA_MORPHING structure [Storage Devices], PFEATURE_DATA_MORPHING, PFEATURE_DATA_MORPHING structure pointer [Storage Devices], _FEATURE_DATA_MORPHING, ntddmmc/FEATURE_DATA_MORPHING, ntddmmc/PFEATURE_DATA_MORPHING, storage.feature_data_morphing, structs-CD-ROM_f159fbd8-73db-440b-a4f3-2429181c6836.xml"
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
-	FEATURE_DATA_MORPHING
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_MORPHING, *PFEATURE_DATA_MORPHING
---

# _FEATURE_DATA_MORPHING structure


## -description


The FEATURE_DATA_MORPHING structure contains information about the morphing feature.


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Asynchronous

Indicates, when set to 1, that the initiator can request device status asynchronously. If set to zero, the initiator must use polling to request status. 


### -field OCEvent


### -field Reserved01


### -field Reserved2

Reserved. 


## -remarks



This structure holds data for the feature named "Morphing" by the <i>MMC-3 </i>specification. Devices that support this feature can notify the initiator of operational changes and allow the initiator to prevent operational changes. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

