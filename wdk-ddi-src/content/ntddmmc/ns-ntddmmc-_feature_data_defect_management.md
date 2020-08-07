---
UID: NS:ntddmmc._FEATURE_DATA_DEFECT_MANAGEMENT
title: _FEATURE_DATA_DEFECT_MANAGEMENT (ntddmmc.h)
description: The FEATURE_DATA_DEFECT_MANAGEMENT structure contains information for the Defect Management feature.
old-location: storage\feature_data_defect_management.htm
tech.root: storage
ms.assetid: ff032dbd-8c84-4442-bbd5-a27b61617d47
ms.date: 03/29/2018
keywords: ["FEATURE_DATA_DEFECT_MANAGEMENT structure"]
ms.keywords: "*PFEATURE_DATA_DEFECT_MANAGEMENT, FEATURE_DATA_DEFECT_MANAGEMENT, FEATURE_DATA_DEFECT_MANAGEMENT structure [Storage Devices], PFEATURE_DATA_DEFECT_MANAGEMENT, PFEATURE_DATA_DEFECT_MANAGEMENT structure pointer [Storage Devices], _FEATURE_DATA_DEFECT_MANAGEMENT, ntddmmc/FEATURE_DATA_DEFECT_MANAGEMENT, ntddmmc/PFEATURE_DATA_DEFECT_MANAGEMENT, storage.feature_data_defect_management, structs-CD-ROM_3c73a6a8-5a76-4a73-b3fa-cae137659fad.xml"
f1_keywords:
 - "ntddmmc/FEATURE_DATA_DEFECT_MANAGEMENT"
 - "FEATURE_DATA_DEFECT_MANAGEMENT"
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
- FEATURE_DATA_DEFECT_MANAGEMENT
targetos: Windows
req.typenames: FEATURE_DATA_DEFECT_MANAGEMENT, *PFEATURE_DATA_DEFECT_MANAGEMENT
---

# _FEATURE_DATA_DEFECT_MANAGEMENT structure


## -description


The FEATURE_DATA_DEFECT_MANAGEMENT structure contains information for the Defect Management feature. 


## -struct-fields




### -field Header

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Reserved1

Reserved.


### -field SupplimentalSpareArea

Indicates, when set to 1, that the logical unit supports the READ DVD STRUCTURE command with a format code of 0Ah. See the <i>SCSI Multimedia - 4 (MMC-4)</i> specification for more information.


### -field Reserved2

Reserved. 


## -remarks



This structure holds data for the feature named "Defect Management" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature are able to provide contiguous address space that is guaranteed to be defect free. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>
 

 

