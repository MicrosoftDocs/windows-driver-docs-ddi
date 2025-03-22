---
UID: NS:ufs.UFS_DEVICE_DESCRIPTOR
title: UFS_DEVICE_DESCRIPTOR (ufs.h)
description: UFS_DEVICE_DESCRIPTOR is the main descriptor for Universal Flash Storage (UFS) devices and should be the first descriptor retrieved as it specifies the device class and sub-class and the protocol (command set) to use to access this device and the maximum number of logical units (LUs) contained within the device.
old-location: storage\ufs_device_descriptor.htm
tech.root: storage
ms.date: 03/07/2024
keywords: ["UFS_DEVICE_DESCRIPTOR structure"]
ms.keywords: "*PUFS_DEVICE_DESCRIPTOR, PUFS_DEVICE_DESCRIPTOR, PUFS_DEVICE_DESCRIPTOR structure pointer [Storage Devices], UFS_DEVICE_DESCRIPTOR, UFS_DEVICE_DESCRIPTOR structure [Storage Devices], storage.ufs_device_descriptor, ufs/PUFS_DEVICE_DESCRIPTOR, ufs/UFS_DEVICE_DESCRIPTOR"
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
req.typenames: UFS_DEVICE_DESCRIPTOR, *PUFS_DEVICE_DESCRIPTOR
f1_keywords:
 - PUFS_DEVICE_DESCRIPTOR
 - ufs/PUFS_DEVICE_DESCRIPTOR
 - UFS_DEVICE_DESCRIPTOR
 - ufs/UFS_DEVICE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ufs.h
api_name:
 - PUFS_DEVICE_DESCRIPTOR
 - UFS_DEVICE_DESCRIPTOR
---

# UFS_DEVICE_DESCRIPTOR structure (ufs.h)



## -description

**UFS_DEVICE_DESCRIPTOR** is the main descriptor for Universal Flash Storage (UFS) devices and should be the first descriptor retrieved as it specifies the device class and sub-class and the protocol (command set) to use to access this device and the maximum number of logical units (LUs) contained within the device.

## -struct-fields

### -field bLength

Specifies the length, in bytes, of this descriptor.

### -field bDescriptorIDN

Specifies the type of the descriptor. This descriptor will have a value of **UFS_DESC_DEVICE_IDN**.

### -field bDevice

Specifies the device type.

| Value | Description |
|--|--|
| 0x00 | Device |
| All other values | Reserved for future use |

### -field bDeviceClass

Specifies the device class.

| Value | Description |
|--|--|
| 0x00 | Mass Storage |
| All other values | Reserved for future use |

### -field bDeviceSubClass

Specifies the UFS mass storage subclasses in a bit map as follows:

| Bit | Value |
|--|--|
| 0 | Bootable or Non-Bootable |
| 1 | Embedded or Removable |
| 2 | Reserved for JESD220-1 (UME) |
| All other values | Reserved for future use |

### -field bProtocol

Specifies the protocol support by the UFS device.

| Value | Description |
|--|--|
| 0x00 | SCSI |
| All other values | Reserved for future use |

### -field bNumberLU

Specifies the number of logical units. This does not include the number of well known logical units.

### -field bNumberWLU

Specifies the number of well known logical units.

### -field bBootEnable

Specifies if a device's boot feature is enabled.

| Value | Description |
|--|--|
| 0x00 | Boot feature disabled |
| 0x01 | Boot feature enabled |
| All other values | Reserved for future use |

### -field bDescrAccessEn

Indicates whether the device descriptor can be read after the partial initialization phase of the boot sequence.

| Value | Description |
|--|--|
| 0x00 | Device Descriptor access disabled |
| 0x01 | Device Descriptor access enabled |
| All other values | Reserved for future use |

### -field bInitPowerMode

**bInitPowerMode** defines the power mode after device initialization or hardware reset.

| Value | Description |
|--|--|
| 0x00 | UFS-Sleep mode |
| 0x01 | Active-mode |
| All other values | Reserved for future use |

### -field bHighPriorityLUN

**bHighPriorityLUN** defines the high priority logical unit.

### -field bSecureRemovalType

Specifies the secure removal type.

| Value | Description |
|--|--|
| 0x00 | Information removed by an erase of the physical memory |
| 0x01 | Information removed by overwriting the addressed locations with a single character followed by an erase |
| 0x02 | Information removed by overwriting the addressed locations with a character, its complement, then a random character |
| 0x03 | Information removed using a vendor defined mechanism. |
| All other values | Reserved for future use |

### -field bSecurityLU

Specifies if there is support for security logical units.

| Value | Description |
|--|--|
| 0x00 | Not supported |
| 0x01 | Replay Protected Memory Block (RPMB) |
| All other values | Reserved for future use |

### -field bBackgroundOpsTermLat

**bBackgroundOpsTermLat** defines the maximum latency for starting data transmission when background operations are ongoing. The termination latency limit applies to two cases:

- When the device receives a COMMAND UFS Protocol Information Units (UPIU) with a transfer request. The device shall start the data transfer and send a DATA IN UPIU or a RTT UPIU within the latency limit.
- When the device receives QUERY REQUEST UPIU to clear the **fBackgroundOpsEn** Flag. The device is expected to terminate background operations within the latency limit.

### -field bInitActiveICCLevel

**bInitActiveICCLevel** defines the **bActiveICCLevel** value after power on or reset. The range of the value is from 0x00 to 0x0F.

### -field wSpecVersion[2]

Indicates the specification version in binary coded decimal (BCD) format.

### -field wManufactureDate[2]

Specifies the manufacturing date in BCD format as 0xMMYY.

### -field iManufacturerName

Contains an index value to the string which contains the manufacturer's name.

### -field iProductName

Contains an index value to the string which contains the product's name.

### -field iSerialNumberID

Contains an index value to the string which contains the serial number.

### -field iOemID

Contains an index value to the string which contains the OEM ID.

### -field wManufacturerID[2]

Specifies the manufacturer ID of the device.

### -field bUD0BaseOffset

Specifies the offset of unit descriptor 0's configurable parameters within the configuration descriptor, **[UFS_CONFIG_DESCRIPTOR](ns-ufs-ufs_config_descriptor.md)**.

### -field bUDConfigPLength

Total size of a **UFS_UNIT_CONFIG_DESCRIPTOR**'s parameters.

### -field bDeviceRTTCap

Specifies the maximum number of outstanding READY TO TRANSFER UPIU'S supported by device. The minimum value is 2.

### -field wPeriodicRTCUpdate[2]

Specifies the frequency and method of real-time clock updates. Bits 10 to 15 are reserved.

### -field bUFSFeaturesSupport

Specifies which features are supported on this device. A feature is supported if its related bit is set to 1.

| Bit | Value |
|--|--|
| 0 | Field Firmware Update (FFU) |
| 1 | Production State Awareness (PSA) |
| 2 | Device Life Span |
| All other values | Reserved for future use |

### -field bFFUTimeout

The maximum time, in seconds, to which access to the device is limited or not possible through any ports associated due to execution of a WRITE BUFFER command.

### -field bQueueDepth

Specifies the queue depth. If this member is equal to 0, the device implements the per-LU queuing architecture.

### -field wDeviceVersion[2]

Specifies the device version.

### -field bNumSecureWPArea

Specifies the total number of secure write protect areas supported by the device. The value of this member is between **bNumberLU** and 32.

### -field dPSAMaxDataSize[4]

Specifies the maximum amount of data that can be written during the pre-soldering phase of the PSA flow.

### -field dPSAStateTimeout

This member corresponds to **bPSAStateTimeout** (29h) in the [JEDEC](https://www.jedec.org/) specification.

### -field iProductRevisionLevel

Specifies the index to the string which contains the product revision level.

### -field Reserved[5]

Reserved for future use.

### -field Reserved2[16]

Reserved for future use.

### -field wHPBVersion

Specifies the host performance booster version.

### -field bHPBControl

### -field Reserved3[12]

Reserved for future use.

### -field dExtendedUFSFeaturesSupport[4]

**dExtendedUFSFeaturesSupport** is a bitmask indicating which extended features are supported.

### -field bWriteBoosterBufferPreserveUserSpaceEn

Setting **bWriteBoosterBufferPreserveUserSpaceEn** to 0x01 avoids the reduction of the total user space that can be configured during provisioning, but might result in lower performance. If **bWriteBoosterBufferPreserveUserSpaceEn** is set to 0x00, the write booster buffer reduces the total user space that can be configured during provisioning.

### -field bWriteBoosterBufferType

**bWriteBoosterBufferType** configures the the write booster buffer type. A value of 0x00 specifies logical unit dedicated buffer mode. A value of 0x01 specifies shared buffer mode.

### -field dNumSharedWriteBoosterBufferAllocUnits[4]

**dNumSharedWriteBoosterBufferAllocUnits** specifies the write booster buffer size for a shared write booster buffer configuration.

## -remarks

If **bBootEnable** in the **UFS_DEVICE_DESCRIPTOR** is set to zero or if the *Boot Well Known Logical Unit* is not mapped to an enabled logical unit, then the *Boot Well Known Logical Unit* shall terminate.

**UFS_DEVICE_DESCRIPTOR** is read only, some of its parameters may be changed by changing the corresponding parameter in **[UFS_UNIT_CONFIG_DESCRIPTOR](ns-ufs-ufs_unit_config_descriptor.md)**.

## -see-also

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
