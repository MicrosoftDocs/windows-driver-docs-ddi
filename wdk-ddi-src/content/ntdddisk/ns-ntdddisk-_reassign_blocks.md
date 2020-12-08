---
UID: NS:ntdddisk._REASSIGN_BLOCKS
title: _REASSIGN_BLOCKS (ntdddisk.h)
description: The REASSIGN_BLOCKS structure is used in conjunction with the IOCTL_DISK_REASSIGN_BLOCKS request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks.
old-location: storage\reassign_blocks.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["REASSIGN_BLOCKS structure"]
ms.keywords: "*PREASSIGN_BLOCKS, PREASSIGN_BLOCKS, PREASSIGN_BLOCKS structure pointer [Storage Devices], REASSIGN_BLOCKS, REASSIGN_BLOCKS structure [Storage Devices], _REASSIGN_BLOCKS, ntdddisk/PREASSIGN_BLOCKS, ntdddisk/REASSIGN_BLOCKS, storage.reassign_blocks, structs-disk_dbe1fcc8-083e-41c4-8620-b216cdbecd34.xml"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
req.typenames: REASSIGN_BLOCKS, *PREASSIGN_BLOCKS
f1_keywords:
 - _REASSIGN_BLOCKS
 - ntdddisk/_REASSIGN_BLOCKS
 - PREASSIGN_BLOCKS
 - ntdddisk/PREASSIGN_BLOCKS
 - REASSIGN_BLOCKS
 - ntdddisk/REASSIGN_BLOCKS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - REASSIGN_BLOCKS
---

# _REASSIGN_BLOCKS structure


## -description

The <b>REASSIGN_BLOCKS</b> structure is used in conjunction with the <a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_reassign_blocks">IOCTL_DISK_REASSIGN_BLOCKS</a> request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks.

## -struct-fields

### -field Reserved

Reserved for system use.

### -field Count

Contains the number of blocks in the array pointed to by <b>BlockNumber</b> to reassign.

### -field BlockNumber

Contains an array of block numbers corresponding to damaged blocks. These numbers will be reassigned to good blocks taken from the device's spare block pool.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_reassign_blocks">IOCTL_DISK_REASSIGN_BLOCKS</a>
