---
UID: NS:scsi.__unnamed_struct_24
title: BLOCK_DEVICE_RANGE_DESCRIPTOR (scsi.h)
description: The BLOCK_DEVICE_RANGE_DESCRIPTOR structure (scsi.h) describes a range of logical blocks associated with the fragments of a file.
tech.root: storage
ms.date: 09/19/2022
keywords: ["BLOCK_DEVICE_RANGE_DESCRIPTOR structure"]
ms.keywords: "*PBLOCK_DEVICE_RANGE_DESCRIPTOR, BLOCK_DEVICE_RANGE_DESCRIPTOR, BLOCK_DEVICE_RANGE_DESCRIPTOR structure [Storage Devices], PBLOCK_DEVICE_RANGE_DESCRIPTOR, PBLOCK_DEVICE_RANGE_DESCRIPTOR structure pointer [Storage Devices], scsi/BLOCK_DEVICE_RANGE_DESCRIPTOR, scsi/PBLOCK_DEVICE_RANGE_DESCRIPTOR, storage.block_device_range_descriptor"
req.header: scsi.h
req.include-header: Scsi.h, Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.typenames: BLOCK_DEVICE_RANGE_DESCRIPTOR, *PBLOCK_DEVICE_RANGE_DESCRIPTOR
f1_keywords:
 - PBLOCK_DEVICE_RANGE_DESCRIPTOR
 - scsi/PBLOCK_DEVICE_RANGE_DESCRIPTOR
 - BLOCK_DEVICE_RANGE_DESCRIPTOR
 - scsi/BLOCK_DEVICE_RANGE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - PBLOCK_DEVICE_RANGE_DESCRIPTOR
 - BLOCK_DEVICE_RANGE_DESCRIPTOR
---

## -description

The **BLOCK_DEVICE_RANGE_DESCRIPTOR** structure describes a range of logical blocks associated with various fragments of a file for an offload copy operation.

## -struct-fields

### -field LogicalBlockAddress

The starting logical block address of a block range.

### -field TransferLength

The length, in logical blocks, of the block range.

### -field Reserved

Reserved bytes.

## -remarks

If *TransferLength* is set to 0, the range descriptor is considered valid and does not cause an error when included in a token parameter list. No operation will be performed for this descriptor.

All multibyte values are in big endian format. Prior to setting, these values must be converted from the endian format of the current platform.

## -see-also

[**POPULATE_TOKEN_HEADER**](/windows-hardware/drivers/ddi/storport/ns-storport-populate_token_header)

[**WRITE_USING_TOKEN_HEADER**](/windows-hardware/drivers/ddi/minitape/ns-minitape-write_using_token_header)
