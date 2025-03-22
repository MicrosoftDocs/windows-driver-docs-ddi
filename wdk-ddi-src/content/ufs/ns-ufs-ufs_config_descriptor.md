---
UID: NS:ufs.UFS_CONFIG_DESCRIPTOR
title: UFS_CONFIG_DESCRIPTOR (ufs.h)
description: The UFS_CONFIG_DESCRIPTOR structure describes the modifiable values of the default device configuration set by the manufacturer.
old-location: storage\ufs_config_descriptor.htm
tech.root: storage
ms.date: 02/29/2024
keywords: ["UFS_CONFIG_DESCRIPTOR structure"]
ms.keywords: "*PUFS_CONFIG_DESCRIPTOR, PUFS_CONFIG_DESCRIPTOR, PUFS_CONFIG_DESCRIPTOR structure pointer [Storage Devices], UFS_CONFIG_DESCRIPTOR, UFS_CONFIG_DESCRIPTOR structure [Storage Devices], storage.ufs_config_descriptor, ufs/PUFS_CONFIG_DESCRIPTOR, ufs/UFS_CONFIG_DESCRIPTOR"
req.header: ufs.h
req.construct-type: structure
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
req.typenames: UFS_CONFIG_DESCRIPTOR, *PUFS_CONFIG_DESCRIPTOR
f1_keywords:
 - PUFS_CONFIG_DESCRIPTOR
 - ufs/PUFS_CONFIG_DESCRIPTOR
 - UFS_CONFIG_DESCRIPTOR
 - ufs/UFS_CONFIG_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ufs.h
api_name:
 - PUFS_CONFIG_DESCRIPTOR
 - UFS_CONFIG_DESCRIPTOR
---

# UFS_CONFIG_DESCRIPTOR structure (ufs.h)



## -description

The **UFS_CONFIG_DESCRIPTOR** structure describes the modifiable values of the default device configuration set by the manufacturer.

## -struct-fields

### -field bLength

Specifies the size, in bytes, of this descriptor.

### -field bDescriptorIDN

Specifies the Configuration Descriptor Type Identifier. This descriptor will have a value of **UFS_DESC_CONFIGURATION_IDN**.

### -field bConfDescContinue

Specifies if a device's configuration descriptor continue feature is enabled.

### -field bBootEnable

Specifies if a device's boot feature is enabled.

### -field bDescrAccessEn

Enables access to the Device Descriptor after the partial initialization phase of the boot sequence.

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

### -field UnitConfig[UFS_MAX_NUM_LU]

Contains the configurable parameters of the unit descriptor.

## -see-also

- **[UFS_UNIT_CONFIG_DESCRIPTOR](/windows-hardware/drivers/ddi/ufs/ns-ufs-ufs_unit_config_descriptor)**
