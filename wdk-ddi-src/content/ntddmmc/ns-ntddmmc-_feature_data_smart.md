---
UID: NS:ntddmmc._FEATURE_DATA_SMART
title: _FEATURE_DATA_SMART (ntddmmc.h)
description: The FEATURE_DATA_SMART structure holds data for the S.M.A.R.T. feature.
old-location: storage\feature_data_smart.htm
tech.root: storage
ms.assetid: cf6578d1-e455-4bbe-a89f-bc0292e24a4a
ms.date: 03/29/2018
keywords: ["FEATURE_DATA_SMART structure"]
ms.keywords: "*PFEATURE_DATA_SMART, FEATURE_DATA_SMART, FEATURE_DATA_SMART structure [Storage Devices], PFEATURE_DATA_SMART, PFEATURE_DATA_SMART structure pointer [Storage Devices], _FEATURE_DATA_SMART, ntddmmc/FEATURE_DATA_SMART, ntddmmc/PFEATURE_DATA_SMART, storage.feature_data_smart, structs-CD-ROM_3d912360-2734-4d01-b7ef-298d90be28b7.xml"
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
targetos: Windows
req.typenames: FEATURE_DATA_SMART, *PFEATURE_DATA_SMART
f1_keywords:
 - _FEATURE_DATA_SMART
 - ntddmmc/_FEATURE_DATA_SMART
 - PFEATURE_DATA_SMART
 - ntddmmc/PFEATURE_DATA_SMART
 - FEATURE_DATA_SMART
 - ntddmmc/FEATURE_DATA_SMART
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - FEATURE_DATA_SMART
---

# _FEATURE_DATA_SMART structure


## -description

The FEATURE_DATA_SMART structure holds data for the S.M.A.R.T. feature.

## -struct-fields

### -field Header

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor.

### -field FaultFailureReportingPagePresent

Indicates, when set to 1, that the device supports the Fault / Failure Reporting Mode. If set to zero, the device does not support this mode.

### -field Reserved1

Reserved.

### -field Reserved02

Reserved.

## -remarks

This structure holds data for the feature named "S.M.A.R.T." by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature support Self-Monitoring Analysis and Reporting Technology (SMART).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>

