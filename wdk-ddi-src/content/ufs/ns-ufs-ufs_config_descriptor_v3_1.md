---
UID: NS:ufs.UFS_CONFIG_DESCRIPTOR_V3_1
tech.root: storage
title: UFS_CONFIG_DESCRIPTOR_V3_1
ms.date: 03/11/2024
targetos: Windows
description: 
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
req.typenames: UFS_CONFIG_DESCRIPTOR_V3_1, *PUFS_CONFIG_DESCRIPTOR_V3_1
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
 - UFS_CONFIG_DESCRIPTOR_V3_1
 - PUFS_CONFIG_DESCRIPTOR_V3_1
f1_keywords:
 - UFS_CONFIG_DESCRIPTOR_V3_1
 - ufs/UFS_CONFIG_DESCRIPTOR_V3_1
 - PUFS_CONFIG_DESCRIPTOR_V3_1
 - ufs/PUFS_CONFIG_DESCRIPTOR_V3_1
dev_langs:
 - c++
helpviewer_keywords:
 - UFS_CONFIG_DESCRIPTOR_V3_1
---

# UFS_CONFIG_DESCRIPTOR_V3_1 structure (ufs.h)

## -description

## -struct-fields

### -field bLength

Specifies the size, in bytes, of this descriptor.

### -field bDescriptorIDN

Specifies the configuration descriptor type identifier. This descriptor will have a value of UFS_DESC_CONFIGURATION_IDN.

### -field bConfDescContinue

Specifies if a device's configuration descriptor continue feature is enabled.

### -field bBootEnable

Specifies if a device's boot feature is enabled.

### -field bDescrAccessEn

Enables access to the device descriptor after the partial initialization phase of the boot sequence.

### -field bInitPowerMode

Specifies the power mode after device initialization or hardware reset.

### -field bHighPriorityLUN

**bHighPriorityLUN** configures the high priority logical unit.

### -field bSecureRemovalType

Configures the secure removal type.

### -field bInitActiveICCLevel

Configures the ICC level in Active mode after device initialization or hardware reset.

### -field wPeriodicRTCUpdate[2]

Specifies the frequency and method of real-time clock updates.

### -field Reserved2[1]

Reserved for future use.

### -field bRPMBRegionEnable

Specifies if Replay Protected Memory Blocks (RPMB) are enabled.

### -field bRPMBRegion1Size

Specifies the size of RPMB region 1.

### -field bRPMBRegion2Size

Specifies the size of RPMB region 2.

### -field bRPMBRegion3Size

Specifies the size of RPMB region 3.

### -field bWriteBoosterBufferPreserveUserSpaceEn

Setting **bWriteBoosterBufferPreserveUserSpaceEn** to 0x01 avoids the reduction of the total user space that can be configured during provisioning, but might result in lower performance. If **bWriteBoosterBufferPreserveUserSpaceEn** is set to 0x00, the write booster buffer reduces the total user space that can be configured during provisioning.

### -field bWriteBoosterBufferType

**bWriteBoosterBufferType** configures the the write booster buffer type. A value of 0x00 specifies logical unit dedicated buffer mode. A value of 0x01 specifies shared buffer mode.

### -field dNumSharedWriteBoosterBufferAllocUnits

**dNumSharedWriteBoosterBufferAllocUnits** specifies the write booster buffer size for a shared write booster buffer configuration.

### -field UnitConfig[UFS_MAX_NUM_LU]

Contains the configurable parameters of the unit descriptor.

## -remarks

If **bBootEnable** is set to zero or if the *Boot Well Known Logical Unit* is not mapped to an enabled logical unit, then the *Boot Well Known Logical Unit* shall terminate.

**UFS_DEVICE_DESCRIPTOR** is read only, some of its parameters may be changed by changing the corresponding parameter in **[UFS_UNIT_CONFIG_DESCRIPTOR_V3_1](ns-ufs-ufs_unit_config_descriptor_v3_1.md)**.

## -see-also

- **[UFS_UNIT_CONFIG_DESCRIPTOR_V3_1](ns-ufs-ufs_unit_config_descriptor_v3_1.md)**
- **[UFS_CONFIG_DESCRIPTOR](ns-ufs-ufs_config_descriptor.md)**
- **[UFS_DEVICE_HEALTH_DESCRIPTOR](ns-ufs-ufs_device_health_descriptor.md)**
- **[UFS_GEOMETRY_DESCRIPTOR](ns-ufs-ufs_geometry_descriptor.md)**
- **[UFS_INTERCONNECT_DESCRIPTOR](ns-ufs-ufs_interconnect_descriptor.md)**
- **[UFS_POWER_DESCRIPTOR](ns-ufs-ufs_power_descriptor.md)**
- **[UFS_RPMB_UNIT_DESCRIPTOR](ns-ufs-ufs_rpmb_unit_descriptor.md)**
- **[UFS_STRING_DESCRIPTOR](ns-ufs-_ufs_string_descriptor.md)**
- **[UFS_UNIT_CONFIG_DESCRIPTOR](ns-ufs-ufs_unit_config_descriptor.md)**
- **[UFS_UNIT_DESCRIPTOR](ns-ufs-ufs_unit_descriptor.md)**
- [Universal Flash Storage 4.0 specification](https://www.jedec.org/standards-documents/docs/jesd220f)
