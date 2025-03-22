---
UID: NS:ufs.UFS_UNIT_CONFIG_DESCRIPTOR_V3_1
tech.root: storage
title: UFS_UNIT_CONFIG_DESCRIPTOR_V3_1
ms.date: 03/11/2024
targetos: Windows
description: The UFS_UNIT_CONFIG_DESCRIPTOR_V3_1 structure describes the user-configurable parameters within the UFS_CONFIG_DESCRIPTOR_V3_1 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ufs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: UFS_UNIT_CONFIG_DESCRIPTOR_V3_1, *PUFS_UNIT_CONFIG_DESCRIPTOR_V3_1
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ufs.h
api_name:
 - UFS_UNIT_CONFIG_DESCRIPTOR_V3_1
 - PUFS_UNIT_CONFIG_DESCRIPTOR_V3_1
f1_keywords:
 - UFS_UNIT_CONFIG_DESCRIPTOR_V3_1
 - ufs/UFS_UNIT_CONFIG_DESCRIPTOR_V3_1
 - PUFS_UNIT_CONFIG_DESCRIPTOR_V3_1
 - ufs/PUFS_UNIT_CONFIG_DESCRIPTOR_V3_1
dev_langs:
 - c++
helpviewer_keywords:
 - UFS_UNIT_CONFIG_DESCRIPTOR_V3_1
---

# UFS_UNIT_CONFIG_DESCRIPTOR_V3_1 structure (ufs.h)

## -description

The **UFS_UNIT_CONFIG_DESCRIPTOR_V3_1** structure describes the user-configurable parameters within the **[UFS_CONFIG_DESCRIPTOR_V3_1](ns-ufs-ufs_config_descriptor_v3_1.md)** structure.

## -struct-fields

### -field bLUEnable

Specifies whether the logical unit is enabled.

### -field bBootLunID

Specifies whether the logical unit is a bootable logical unit.

### -field bLUWriteProtect

Specifies whether the Logical Unit is write protected.

### -field bMemoryType

Specifies the Memory type of the device. Can be one of the following values.

| Value | Description |
|--|--|
| 0x00 | Normal Memory type |
| 0x01 | System code memory type |
| 0x02 | Non-Persistent memory type |
| 0x03 | Enhanced memory type 1 |
| 0x04 | Enhanced memory type 2 |
| 0x05 | Enhanced memory type 3 |
| 0x06 | Enhanced memory type 4 |
| All other values | Reserved for future use. |

### -field dNumAllocUnits[4]

Specifies the number of allocation units assigned to the logical unit.

### -field bDataReliability

**bDataReliability** defines the device behavior when a power failure occurs during a write operation to the logical unit. Can be one of the following values.

| Value | Description |
|--|--|
| 0x00 | The logical unit is not protected; thus its entire data may be lost as a result of a power failure during a write operation. |
| 0x01 | The logical unit is protected; thus its data is protected against power failure. |
| All other values | Reserved for future use. |

### -field bLogicalBlockSize

Specifies the logical block size.

### -field bProvisioningType

Specifies the provisioning type.

### -field wContextCapabilities[2]

Specifies the number of contexts to be supported in each logical unit.

### -field Reserved[3]

Reserved for future use.

### -field wLUMaxActiveHPBRegions

Specifies the maximum number of HPB regions assigned to the HPB logical unit.

### -field wHPBPinnedRegionStartIdx

Specifies the  HPB pinned region start offset.

### -field wNumHPBPinnedRegions

Specifies the number of HPB pinned regions assigned to the HPB logical unit.

### -field dLUNumWriteBoosterBufferAllocUnits

Specifies the number of logical unit WriteBooster buffer allocation units.

## -remarks

## -see-also

- [Universal Flash Storage 4.0 specification](https://www.jedec.org/standards-documents/docs/jesd220f)
