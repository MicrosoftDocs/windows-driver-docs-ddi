---
UID: NS:ntddmmc._FEATURE_DATA_DISC_CONTROL_BLOCKS
title: "_FEATURE_DATA_DISC_CONTROL_BLOCKS"
author: windows-driver-content
description: The FEATURE_DATA_DISC_CONTROL_BLOCKS structure holds an array of the data reported for the Disc Control Block feature.
old-location: storage\feature_data_disc_control_blocks.htm
old-project: storage
ms.assetid: ed39e714-38c5-45cf-b1f0-dd00b4d49895
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_DISC_CONTROL_BLOCKS, FEATURE_DATA_DISC_CONTROL_BLOCKS, FEATURE_DATA_DISC_CONTROL_BLOCKS structure [Storage Devices], PFEATURE_DATA_DISC_CONTROL_BLOCKS, PFEATURE_DATA_DISC_CONTROL_BLOCKS structure pointer [Storage Devices], _FEATURE_DATA_DISC_CONTROL_BLOCKS, ntddmmc/FEATURE_DATA_DISC_CONTROL_BLOCKS, ntddmmc/PFEATURE_DATA_DISC_CONTROL_BLOCKS, storage.feature_data_disc_control_blocks, structs-CD-ROM_313fa292-b1c4-408d-94e9-491cb3d0aa0f.xml"
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
-	FEATURE_DATA_DISC_CONTROL_BLOCKS
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_DISC_CONTROL_BLOCKS, *PFEATURE_DATA_DISC_CONTROL_BLOCKS
---

# _FEATURE_DATA_DISC_CONTROL_BLOCKS structure


## -description


The FEATURE_DATA_DISC_CONTROL_BLOCKS structure holds an array of the data reported for the Disc Control Block feature. 


## -struct-fields




### -field Header

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Data

Contains zero, one, or more disk control blocks. Each disk control block is contained in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553783">FEATURE_DATA_DISC_CONTROL_BLOCKS_EX</a> structure. 


## -remarks



This structure holds data for the feature named "Disc Control Blocks" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can do reads and writes of disc control blocks. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553783">FEATURE_DATA_DISC_CONTROL_BLOCKS_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>
 

 

