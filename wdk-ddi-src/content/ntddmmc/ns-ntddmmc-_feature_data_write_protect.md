---
UID: NS:ntddmmc._FEATURE_DATA_WRITE_PROTECT
title: _FEATURE_DATA_WRITE_PROTECT (ntddmmc.h)
description: The FEATURE_DATA_WRITE_PROTECT structure contains information about the Write Protect feature.
old-location: storage\feature_data_write_protect.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["FEATURE_DATA_WRITE_PROTECT structure"]
ms.keywords: "*PFEATURE_DATA_WRITE_PROTECT, FEATURE_DATA_WRITE_PROTECT, FEATURE_DATA_WRITE_PROTECT structure [Storage Devices], PFEATURE_DATA_WRITE_PROTECT, PFEATURE_DATA_WRITE_PROTECT structure pointer [Storage Devices], _FEATURE_DATA_WRITE_PROTECT, ntddmmc/FEATURE_DATA_WRITE_PROTECT, ntddmmc/PFEATURE_DATA_WRITE_PROTECT, storage.feature_data_write_protect, structs-CD-ROM_67c6f24f-271e-4452-8b5f-fc6719c1d291.xml"
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
req.typenames: FEATURE_DATA_WRITE_PROTECT, *PFEATURE_DATA_WRITE_PROTECT
f1_keywords:
 - _FEATURE_DATA_WRITE_PROTECT
 - ntddmmc/_FEATURE_DATA_WRITE_PROTECT
 - PFEATURE_DATA_WRITE_PROTECT
 - ntddmmc/PFEATURE_DATA_WRITE_PROTECT
 - FEATURE_DATA_WRITE_PROTECT
 - ntddmmc/FEATURE_DATA_WRITE_PROTECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - _FEATURE_DATA_WRITE_PROTECT
 - PFEATURE_DATA_WRITE_PROTECT
 - FEATURE_DATA_WRITE_PROTECT
---

# _FEATURE_DATA_WRITE_PROTECT structure


## -description

The FEATURE_DATA_WRITE_PROTECT structure contains information about the Write Protect feature.

## -struct-fields

### -field Header

Contains a <a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor.

### -field SupportsSWPPBit

Indicates, when set to 1, that the device supports set/release PWP status. If additionally <b>SupportsPersistentWriteProtect</b> is set to 1, the device supports the SEND DVD STRUCTURE command with Format = 0xC0. For more details on the write protect feature see the <i>SCSI Multimedia - 4 (MMC-4)</i> specification.

### -field SupportsPersistentWriteProtect

Indicates, when set to 1, that the device supports the persistent write protect bit of the time-out & protect mode page. For more details on the write protect feature see the <i>SCSI Multimedia - 4 (MMC-4)</i> specification.

### -field WriteInhibitDCB

### -field DiscWriteProtectPAC

### -field Reserved01

### -field Reserved2

Reserved.

## -remarks

This structure holds data for the feature named "Write Protect" by the <i>MMC-3 </i>specification. Devices that support this feature allow the initiator to change the write-protection state of the media programmatically.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_header">FEATURE_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ntddmmc/ne-ntddmmc-_feature_number">FEATURE_NUMBER</a>

