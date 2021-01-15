---
UID: NS:ntddmmc._FEATURE_DATA_DISC_CONTROL_BLOCKS_EX
title: _FEATURE_DATA_DISC_CONTROL_BLOCKS_EX (ntddmmc.h)
description: The FEATURE_DATA_DISC_CONTROL_BLOCKS_EX structure holds the data reported for a Disc Control Block.
old-location: storage\feature_data_disc_control_blocks_ex.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["FEATURE_DATA_DISC_CONTROL_BLOCKS_EX structure"]
ms.keywords: "*PFEATURE_DATA_DISC_CONTROL_BLOCKS_EX, FEATURE_DATA_DISC_CONTROL_BLOCKS_EX, FEATURE_DATA_DISC_CONTROL_BLOCKS_EX structure [Storage Devices], PFEATURE_DATA_DISC_CONTROL_BLOCKS_EX, PFEATURE_DATA_DISC_CONTROL_BLOCKS_EX structure pointer [Storage Devices], _FEATURE_DATA_DISC_CONTROL_BLOCKS_EX, ntddmmc/FEATURE_DATA_DISC_CONTROL_BLOCKS_EX, ntddmmc/PFEATURE_DATA_DISC_CONTROL_BLOCKS_EX, storage.feature_data_disc_control_blocks_ex, structs-CD-ROM_5e32d5eb-6a1d-412d-9efe-dba88f85c730.xml"
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
req.typenames: FEATURE_DATA_DISC_CONTROL_BLOCKS_EX, *PFEATURE_DATA_DISC_CONTROL_BLOCKS_EX
f1_keywords:
 - _FEATURE_DATA_DISC_CONTROL_BLOCKS_EX
 - ntddmmc/_FEATURE_DATA_DISC_CONTROL_BLOCKS_EX
 - PFEATURE_DATA_DISC_CONTROL_BLOCKS_EX
 - ntddmmc/PFEATURE_DATA_DISC_CONTROL_BLOCKS_EX
 - FEATURE_DATA_DISC_CONTROL_BLOCKS_EX
 - ntddmmc/FEATURE_DATA_DISC_CONTROL_BLOCKS_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - _FEATURE_DATA_DISC_CONTROL_BLOCKS_EX
 - PFEATURE_DATA_DISC_CONTROL_BLOCKS_EX
 - FEATURE_DATA_DISC_CONTROL_BLOCKS_EX
---

# _FEATURE_DATA_DISC_CONTROL_BLOCKS_EX structure


## -description

The FEATURE_DATA_DISC_CONTROL_BLOCKS_EX structure holds the data reported for a Disc Control Block.

## -struct-fields

### -field ContentDescriptor

Contains the first of one or more control blocks. The bytes in this array are arranged in big-endian order. <b>ContentDescriptor</b>[0] contains the most significant byte, and <b>ContentDescriptor</b>[3] contains the least significant byte.

## -remarks

This structure holds data for the feature named "Disc Control Blocks" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can read or write Disc Control Blocks.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_feature_data_disc_control_blocks">FEATURE_DATA_DISC_CONTROL_BLOCKS</a>

