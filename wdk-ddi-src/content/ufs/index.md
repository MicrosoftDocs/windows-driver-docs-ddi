---
UID: NA:ufs
ms.assetid: 77c0dfa6-2ceb-31c0-bda9-4c80a5be1c49
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ufs.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Ufs.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [UFS_CONFIG_DESCRIPTOR structure](ns-ufs-ufs_config_descriptor.md) | The UFS_CONFIG_DESCRIPTOR structure describes the modifiable values of the default device configuration set by the manufacturer. |
| [UFS_DEVICE_DESCRIPTOR structure](ns-ufs-ufs_device_descriptor.md) | UFS_DEVICE_DESCRIPTOR is the main descriptor for Universal Flash Storage (UFS) devices and should be the first descriptor retrieved as it specifies the device class and sub-class and the protocol (command set) to use to access this device and the maximum number of logical units contained within the device. |
| [UFS_DEVICE_HEALTH_DESCRIPTOR structure](ns-ufs-ufs_device_health_descriptor.md) | The UFS_DEVICE_HEALTH_DESCRIPTOR structure describes the health of a device. |
| [UFS_GEOMETRY_DESCRIPTOR structure](ns-ufs-ufs_geometry_descriptor.md) | UFS_GEOMETRY_DESCRIPTOR describes a device's geometric parameters. |
| [UFS_INTERCONNECT_DESCRIPTOR structure](ns-ufs-ufs_interconnect_descriptor.md) | UFS_INTERCONNECT_DESCRIPTOR contains the MIPI M-PHY® specification version number and the MIPI 6338 UniPro℠ specification version number. |
| [UFS_POWER_DESCRIPTOR structure](ns-ufs-ufs_power_descriptor.md) | UFS_POWER_DESCRIPTOR contains information about the power capabilities and power states of the device. |
| [UFS_RPMB_UNIT_DESCRIPTOR structure](ns-ufs-ufs_rpmb_unit_descriptor.md) | The UFS_RPMB_UNIT_DESCRIPTOR structure describes the contents of a Replay Protected Memory Block (RBMB) Unit. |
| [UFS_UNIT_CONFIG_DESCRIPTOR structure](ns-ufs-ufs_unit_config_descriptor.md) | The UFS_UNIT_CONFIG_DESCRIPTOR structure describes the user configurable parameters within the UFS_CONFIG_DESCRIPTOR. |
| [UFS_UNIT_DESCRIPTOR structure](ns-ufs-ufs_unit_descriptor.md) | The UFS_UNIT_DESCRIPTOR structure describes a generic unit descriptor. |
| [_UFS_STRING_DESCRIPTOR structure](ns-ufs-_ufs_string_descriptor.md) | The UFS_STRING_DESCRIPTOR structure describes either the Manufacturer Name, Product Name, OEM ID, or Serial Number as a string. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [UFS_ATTRIBUTES_DESCRIPTOR enumeration](ne-ufs-ufs_attributes_descriptor.md) | UFS_ATTRIBUTES_DESCRIPTOR describes the different types of attributes used by Universal Flash Storage (UFS) descriptors. |
| [UFS_FLAGS_DESCRIPTOR enumeration](ne-ufs-ufs_flags_descriptor.md) | UFS_FLAGS_DESCRIPTOR describes the different types of flags used by Universal Flash Storage (UFS) descriptors. |
| [UFS_PURGE_STATUS enumeration](ne-ufs-ufs_purge_status.md) | Specifies the current status of a purge operation. |
