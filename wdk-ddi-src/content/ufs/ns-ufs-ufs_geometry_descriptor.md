---
UID: NS:ufs.UFS_GEOMETRY_DESCRIPTOR
title: UFS_GEOMETRY_DESCRIPTOR (ufs.h)
description: UFS_GEOMETRY_DESCRIPTOR describes a device's geometric parameters.
old-location: storage\ufs_geometry_descriptor.htm
tech.root: storage
ms.date: 03/07/2024
keywords: ["UFS_GEOMETRY_DESCRIPTOR structure"]
ms.keywords: "*PUFS_GEOMETRY_DESCRIPTOR, PUFS_GEOMETRY_DESCRIPTOR, PUFS_GEOMETRY_DESCRIPTOR structure pointer [Storage Devices], UFS_GEOMETRY_DESCRIPTOR, UFS_GEOMETRY_DESCRIPTOR structure [Storage Devices], storage.ufs_geometry_descriptor, ufs/PUFS_GEOMETRY_DESCRIPTOR, ufs/UFS_GEOMETRY_DESCRIPTOR"
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
req.typenames: UFS_GEOMETRY_DESCRIPTOR, *PUFS_GEOMETRY_DESCRIPTOR
f1_keywords:
 - PUFS_GEOMETRY_DESCRIPTOR
 - ufs/PUFS_GEOMETRY_DESCRIPTOR
 - UFS_GEOMETRY_DESCRIPTOR
 - ufs/UFS_GEOMETRY_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ufs.h
api_name:
 - PUFS_GEOMETRY_DESCRIPTOR
 - UFS_GEOMETRY_DESCRIPTOR
---

# UFS_GEOMETRY_DESCRIPTOR structure

## -description

**UFS_GEOMETRY_DESCRIPTOR** describes a device's geometric parameters.

## -struct-fields

### -field bLength

Specifies the length of the descriptor.

### -field bDescriptorIDN

Specifies the type of the descriptor. This descriptor will have a value of **UFS_DESC_GEOMETRY_IDN**.

### -field bMediaTechnology

Reserved for future use.

### -field Reserved1

Reserved for future use.

### -field qTotalRawDeviceCapacity[8]

Specifies the total raw device capacity. Expressed in units of 512 bytes.

### -field bMaxNumberLU

Specifies the maximum number of logical unit(s) supported by the UFS (Universal Flash Storage). Contains one of the following values:

| Value | Description |
|--|--|
| 0x00 | 8 logical units. |
| 0x01 | 32 logical units. |
| Other Values | Reserved for future use. |

### -field dSegmentSize[4]

Specifies the segment size of the device in units of 512 bytes.

### -field bAllocationUnitSize

Specifies the allocation unit size in number of segments.

### -field bMinAddrBlockSize

Specifies the minimum addressable block size in units of 512 bytes. The minimum size is 4 KB or a value of 0x08.

### -field bOptimalReadBlockSize

Specifies the optimal read block size in units of 512 bytes.

### -field bOptimalWriteBlockSize

Specifies the optimal write block size in units of 512 bytes. **bOptimalWriteBlockSize** is equal to or greater than **bMinAddrBlockSize**.

### -field bMaxInBufferSize

Specifies the max size of the data-in buffer in units of 512 bytes. The minium size is 4 KB or a value of 0x08.

### -field bMaxOutBufferSize

Specifies the max size of the data-out buffer in units of 512 bytes. The minium size is 4 KB or a value of 0x08.

### -field bRPMB_ReadWriteSize

Specifies the maximum number of Replay Protected Memory Block (RPMB) frames allowed in Security Protocol In and Security Protocol Out. Each frame is 256-bytes.

### -field bDynamicCapacityResourcePolicy

Specifies a device's spare blocks resource management policy. Contains one of the following values:

| Value | Description |
|--|--|
| 0x00 | Spare blocks resource management policy is per logical unit. |
| 0x01 | Spare blocks resource management policy is per memory type. |

### -field bDataOrdering

Specifies if a device supports out-of-order data transfer. Contains one of the following values:

| Value | Description |
|--|--|
| 0x00 | Out-of-order data transfer is not supported. |
| 0x01 | Out-of-order data transfer is supported. |
| All other values | Reserved for future use. |

### -field bMaxContexIDNumber

Specifies the max number of contexts supported by a device. This number must be greater than 5.

### -field bSysDataTagUnitSize

Specifies the system data tag unit size.

### -field bSysDataTagResSize

Specifies the maximum size in bytes allocated by the device to handle system data.

### -field bSupportedSecRTypes

Specifies the supported Secure Removal types. The first 3 bits of the variable are flags that represent different supported Secure Removal types.

| Bit | Description |
|--|--|
| 0 | Information removed with an erase of the physical memory. |
| 1 | Information removed by overwriting the addressed locations with a single character followed by an erase. |
| 2 | Information removed by overwriting the addressed locations with a character, its complement, then a random character. |
| 3 | Information removed using a vendor-defined mechanism. |
| 4-7 | Reserved for future use. |

### -field wSupportedMemoryTypes[2]

Specifies the supported memory types in a bitmap.

| Bit | Description |
|--|--|
| 0 | A normal memory type is supported. |
| 1 | A system code memory type is supported. |
| 2 | A non-persistent memory type is supported. |
| 3 | Enhanced memory type 1 is supported. |
| 4 | Enhanced memory type 2 is supported. |
| 5 | Enhanced memory type 3 is supported. |
| 6 | Enhanced memory type 4 is supported. |
| 7-14 | Reserved for future use. |
| 15 | A RPMB memory type is supported. |

### -field dSystemCodeMaxNAllocU[4]

Specifies the maximum number of allocation units for the System Code for a device.

### -field wSystemCodeCapAdjFac[2]

Species the Capacity Adjustment Factor for the System Code memory type.

### -field dNonPersistMaxNAllocU[4]

Species the maximum number of Allocation Units for a non-persistent memory type.

### -field wNonPersistCapAdjFac[2]

Specifies the capacity adjustment factor for the non-persistent memory type.

### -field dEnhanced1MaxNAllocU[4]

Specifies the max number of Allocation Units for the enhanced memory type 1.

### -field wEnhanced1CapAdjFac[2]

Specifies the Capacity Adjustment Factor for the enhanced memory type 1.

### -field dEnhanced2MaxNAllocU[4]

Specifies the max number of Allocation Units for the enhanced memory type 2.

### -field wEnhanced2CapAdjFac[2]

Specifies the Capacity Adjustment Factor for the enhanced memory type 2.

### -field dEnhanced3MaxNAllocU[4]

Specifies the max number of Allocation Units for the enhanced memory type 3.

### -field wEnhanced3CapAdjFac[2]

Specifies the Capacity Adjustment Factor for the enhanced memory type 3.

### -field dEnhanced4MaxNAllocU[4]

Specifies the max number of Allocation Units for the enhanced memory type 4.

### -field wEnhanced4CapAdjFac[2]

Specifies the Capacity Adjustment Factor for the enhanced memory type 4.

### -field dOptimalLogicalBlockSize[4]

Specifies the optimal logical block size.

- bit [3:0]: Normal memory type
- bit [7:4]: System code memory type
- bit [11:8]: Non-persistent memory type
- bit [15:12]: Enhanced memory type 1
- bit [19:16]: Enhanced memory type 2
- bit [23:20]: Enhanced memory type 3
- bit [27:24]: Enhanced memory type 4
- bit [31:28]:Reserved

### -field bHPBRegionSize

Specifies the size of the HPB region.

### -field bHPBNumberLU

Specifies the maximum number of logical units in which HPB can be enabled.

### -field bHPBSubRegionSize

Specifies the size of the HPB subregion. The **bHPBSubRegionSize** can't exceed **bHPBRegionSize**.

### -field wDeviceMaxActiveHPBRegions

Specifies the mximum number of active HPB regions supported by the device.

### -field Reserved2[2]

Reserved for future use.

### -field dWriteBoosterBufferMaxNAllocUnits[4]

Specifies the total WriteBooster buffer size supported by the device. The sum of WriteBooster buffer sizes for all LUs is less than or equal to the value indicated by **dWriteBoosterBufferMaxNAllocUnits**.

### -field bDeviceMaxWriteBoosterLUs

Specifies the maximum number of supported WriteBooster buffers.

### -field bWriteBoosterBufferCapAdjFac

Specifies the capacity adjustment factor for the WriteBooster buffer memory type. This value provides the LBA space reduction multiplication factor when WriteBooster Buffer is configured in user space reduction mode. Therefore, this parameter applies only if **bWriteBoosterBufferPreserveUserSpaceEn** is 0x00.

### -field bSupportedWriteBoosterBufferUserSpaceReductionTypes

Specifies the supportability of user space reduction mode and preserve user space mode.

- 0x00: WriteBooster buffer can only be configured in user space reduction type.
- ox01: WriteBooster buffer can only be configured in preserve user space type.
- ox02: Device can be configured in either user space reduction type or preserve user space type.
- Others : Reserved

### -field bSupportedWriteBoosterBufferTypes

Specifies the supportability of WriteBooster buffer type.

- 00h: LU based WriteBooster buffer configuration
- 01h: Single shared WriteBooster buffer configuration
- 02h: Supporting both LU based WriteBooster buffer and single shared WriteBooster buffer configuration
- Others: Reserved

## -remarks

If the size of the data transferred exceeds the number of frames **bRPMB_ReadWriteSize**, it will be done in multiple Security commands.

The Capacity Adjustment Factor value for a normal memory type is equal to one.
