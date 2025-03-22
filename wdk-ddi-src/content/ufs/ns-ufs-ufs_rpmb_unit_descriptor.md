---
UID: NS:ufs.UFS_RPMB_UNIT_DESCRIPTOR
title: UFS_RPMB_UNIT_DESCRIPTOR (ufs.h)
description: The UFS_RPMB_UNIT_DESCRIPTOR structure describes the contents of a Replay Protected Memory Block (RBMB) Unit.
old-location: storage\ufs_rpmb_unit_descriptor.htm
tech.root: storage
ms.date: 03/28/2024
keywords: ["UFS_RPMB_UNIT_DESCRIPTOR structure"]
ms.keywords: "*PUFS_RPMB_UNIT_DESCRIPTOR, PUFS_RPMB_UNIT_DESCRIPTOR, PUFS_RPMB_UNIT_DESCRIPTOR structure pointer [Storage Devices], UFS_RPMB_UNIT_DESCRIPTOR, UFS_RPMB_UNIT_DESCRIPTOR structure [Storage Devices], storage.ufs_rpmb_unit_descriptor, ufs/PUFS_RPMB_UNIT_DESCRIPTOR, ufs/UFS_RPMB_UNIT_DESCRIPTOR"
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
req.typenames: UFS_RPMB_UNIT_DESCRIPTOR, *PUFS_RPMB_UNIT_DESCRIPTOR
f1_keywords:
 - PUFS_RPMB_UNIT_DESCRIPTOR
 - ufs/PUFS_RPMB_UNIT_DESCRIPTOR
 - UFS_RPMB_UNIT_DESCRIPTOR
 - ufs/UFS_RPMB_UNIT_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ufs.h
api_name:
 - PUFS_RPMB_UNIT_DESCRIPTOR
 - UFS_RPMB_UNIT_DESCRIPTOR
---

# UFS_RPMB_UNIT_DESCRIPTOR structure (ufs.h)



## -description

**UFS_RPMB_UNIT_DESCRIPTOR** structure describes the contents of a Replay Protected Memory Block (RBMB) Unit.

## -struct-fields

### -field bLength

Specifies the length, in bytes, of this descriptor.

### -field bDescriptorIDN

Specifies the type of the descriptor. This descriptor will have a value of **UFS_DESC_UNIT_IDN**.

### -field bUnitIndex

Specifies the unit index.

### -field bLUEnable

Specifies if the logic unit number (LUN) is enabled. If **bLUEnable** is equal to 0x00, the logical unit is disabled.

### -field bBootLunID

### -field bLUWriteProtect

Specifies if the logical unit is write-protected. Contains one of the following values:

| Value | Description |
|--|--|
| 0x00 | The logical unit is not write protected. |
| 0x01 | The logical unit is write protected. |
| 0x02 | The logical unit is permanently write protected. |

### -field bLUQueueDepth

Specifies the logical unit queue depth. Can be any value from 0x00 to 0xff.

### -field bPSASensitive

Specifies if the logical unit is sensitive to soldering. Contains one of the following values:

| Value | Description |
|--|--|
| 0x00 | The logical unit is not sensitive to soldering. |
| 0x01 | The logical unit is sensitive to soldering. |

### -field bMemoryType

Specifies the desired memory type. Equal to 0x0F.

### -field Reserved

Reserved for future use.

### -field bLogicalBlockSize

Specifies the logical block size of the descriptor.

### -field qLogicalBlockCount[8]

Specifies the total number of addressable logical blocks in the logical unit.

### -field dEraseBlockSize[4]

Specifies the erase block size.

### -field bProvisioningType

Specifies the provisioning type.

### -field qPhyMemResourceCount[8]

Specifies the total physical memory resources available in the logical unit.

### -field Reserved2[3]

Reserved for future use.
