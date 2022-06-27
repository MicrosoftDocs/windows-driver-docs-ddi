---
UID: NS:storport.__unnamed_struct_26
title: WRITE_USING_TOKEN_HEADER (storport.h)
description: The WRITE_USING_TOKEN_HEADER structure (storport.h) describes the destination data locations for an offload write data operation.
old-location: storage\write_using_token_header.htm
tech.root: storage
ms.date: 05/24/2022
keywords: ["WRITE_USING_TOKEN_HEADER structure"]
ms.keywords: "*PWRITE_USING_TOKEN_HEADER, PWRITE_USING_TOKEN_HEADER, PWRITE_USING_TOKEN_HEADER structure pointer [Storage Devices], WRITE_USING_TOKEN_HEADER, WRITE_USING_TOKEN_HEADER structure [Storage Devices], scsi/PWRITE_USING_TOKEN_HEADER, scsi/WRITE_USING_TOKEN_HEADER, storage.write_using_token_header"
req.header: storport.h
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
req.typenames: WRITE_USING_TOKEN_HEADER, *PWRITE_USING_TOKEN_HEADER
f1_keywords:
 - PWRITE_USING_TOKEN_HEADER
 - storport/PWRITE_USING_TOKEN_HEADER
 - WRITE_USING_TOKEN_HEADER
 - storport/WRITE_USING_TOKEN_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - PWRITE_USING_TOKEN_HEADER
 - WRITE_USING_TOKEN_HEADER
---

# WRITE_USING_TOKEN_HEADER structure (storport.h)

## -description

The **WRITE_USING_TOKEN_HEADER** structure describes the destination data locations for an offload write data operation.  The offload write data operation described by this structure is associated with a token representation of data (ROD).

## -struct-fields

### -field WriteUsingTokenDataLength

The length of this structure beginning with the **Immediate** parameter and include all of the elements of the **BlockDeviceRangeDescriptor** array.

### -field Immediate

If set, the status of the WRITE USING TOKEN command is returned immediately after receipt and validation of the token ROD and range descriptors. Otherwise, status is returned after all command processing is complete.

### -field Reserved1

Reserved bits.

### -field Reserved2

Reserved.

### -field BlockOffsetIntoToken

The offset, in logical blocks,  in the ROD for **Token** indicating the start of the source data for the offload write data operation.

### -field Token

A token created by a previous the POPULATE TOKEN command operation.

### -field Reserved3

Reserved.

### -field BlockDeviceRangeDescriptorListLength

The length, in bytes, for all  of the [**BLOCK_DEVICE_RANGE_DESCRIPTOR**](../scsi/ns-scsi-block_device_range_descriptor.md) structures in the **BlockDeviceRangeDescriptor** array.

### -field BlockDeviceRangeDescriptor

An array of [**BLOCK_DEVICE_RANGE_DESCRIPTOR**](../scsi/ns-scsi-block_device_range_descriptor.md) structures which describe the destination data blocks for the offload write data transfer.

## -remarks

All multibyte values are in big endian format. Prior to setting, these values must be converted from the endian format of the current platform.

## -see-also

[**BLOCK_DEVICE_RANGE_DESCRIPTOR**](../scsi/ns-scsi-block_device_range_descriptor.md)

[**POPULATE_TOKEN_HEADER**](ns-storport-populate_token_header.md)
