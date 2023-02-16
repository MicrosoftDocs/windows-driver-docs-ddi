---
UID: NS:ufs.UFS_UNIT_CONFIG_DESCRIPTOR
title: UFS_UNIT_CONFIG_DESCRIPTOR (ufs.h)
description: The UFS_UNIT_CONFIG_DESCRIPTOR structure describes the user configurable parameters within the UFS_CONFIG_DESCRIPTOR.
old-location: storage\ufs_unit_config_descriptor.htm
tech.root: storage
ms.date: 05/13/2021
keywords: ["UFS_UNIT_CONFIG_DESCRIPTOR structure"]
ms.keywords: "*PUFS_UNIT_CONFIG_DESCRIPTOR, PUFS_UNIT_CONFIG_DESCRIPTOR, PUFS_UNIT_CONFIG_DESCRIPTOR structure pointer [Storage Devices], UFS_UNIT_CONFIG_DESCRIPTOR, UFS_UNIT_CONFIG_DESCRIPTOR structure [Storage Devices], storage.ufs_unit_config_descriptor, ufs/PUFS_UNIT_CONFIG_DESCRIPTOR, ufs/UFS_UNIT_CONFIG_DESCRIPTOR"
req.header: ufs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.typenames: UFS_UNIT_CONFIG_DESCRIPTOR, *PUFS_UNIT_CONFIG_DESCRIPTOR
f1_keywords:
 - PUFS_UNIT_CONFIG_DESCRIPTOR
 - ufs/PUFS_UNIT_CONFIG_DESCRIPTOR
 - UFS_UNIT_CONFIG_DESCRIPTOR
 - ufs/UFS_UNIT_CONFIG_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ufs.h
api_name:
 - PUFS_UNIT_CONFIG_DESCRIPTOR
 - UFS_UNIT_CONFIG_DESCRIPTOR
---

# UFS_UNIT_CONFIG_DESCRIPTOR structure


## -description

The **UFS_UNIT_CONFIG_DESCRIPTOR** structure describes the user-configurable parameters within the [**UFS_CONFIG_DESCRIPTOR**](ns-ufs-ufs_config_descriptor.md) structure.

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
| ----- | ----------- |
| 0x00  | Normal Memory type |
| 0x01  | System code memory type |
| 0x02  | Non-Persistent memory type |
| 0x03  | Enhanced memory type 1 |
| 0x04  | Enhanced memory type 2 |
| 0x05  | Enhanced memory type 3 |
| 0x06  | Enhanced memory type 4 |
| All other values | Reserved for future use. |

### -field dNumAllocUnits

Specifies the number of allocation units assigned to the logical unit.

### -field bDataReliability

**bDataReliability** defines the device behavior when a power failure occurs during a write operation to the logical unit. Can be one of the following values.

| Value | Description |
| ----- | ----------- |
| 0x00  | The logical unit is not protected; thus its entire data may be lost as a result of a power failure during a write operation. |
| 0x01  | The logical unit is protected; thus its data is protected against power failure. |
| All other values | Reserved for future use. |

### -field bLogicalBlockSize

Specifies the logical block size.

### -field bProvisioningType

Specifies the provisioning type. Can be one of the following values.

| Value | Description |
| ----- | ----------- |
| 0x00  | Thin Provisioning is disabled (default) |
| 0x02  | Thin Provisioning is enabled and Thin Provisioning Read Zeros (TPRZ) = 0 |
| 0x03  | Thin Provisioning is enabled and TPRZ = 1 |
| All other values | Reserved for future use. |

### -field wContextCapabilities

Specifies the Context Capabilities.

### -field Reserved

Reserved for future use.

### -field wLUMaxActiveHPBRegions

### -field wHPBPinnedRegionStartIdx

### -field wNumHPBPinnedRegions

### -field Reserved2

Reserved for future use.

## -see-also

[**UFS_CONFIG_DESCRIPTOR**](ns-ufs-ufs_config_descriptor.md)

