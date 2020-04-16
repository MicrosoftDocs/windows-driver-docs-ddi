---
UID: NS:storport.__unnamed_struct_17
title: WRITE_USING_TOKEN_HEADER (storport.h)
description: The WRITE_USING_TOKEN_HEADER structure describes the destination data locations for an offload write data operation.
old-location: storage\write_using_token_header.htm
tech.root: storage
ms.assetid: A46ED23A-7DB0-4792-B903-F748BCDAD55E
ms.date: 03/29/2018
keywords: ["WRITE_USING_TOKEN_HEADER structure"]
ms.keywords: "*PWRITE_USING_TOKEN_HEADER, PWRITE_USING_TOKEN_HEADER, PWRITE_USING_TOKEN_HEADER structure pointer [Storage Devices], WRITE_USING_TOKEN_HEADER, WRITE_USING_TOKEN_HEADER structure [Storage Devices], scsi/PWRITE_USING_TOKEN_HEADER, scsi/WRITE_USING_TOKEN_HEADER, storage.write_using_token_header"
f1_keywords:
 - "storport/WRITE_USING_TOKEN_HEADER"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- scsi.h
api_name:
- WRITE_USING_TOKEN_HEADER
product:
- Windows
targetos: Windows
req.typenames: WRITE_USING_TOKEN_HEADER, *PWRITE_USING_TOKEN_HEADER
---

# WRITE_USING_TOKEN_HEADER structure


## -description


The <b>WRITE_USING_TOKEN_HEADER</b> structure describes the destination data locations for an offload write data operation.  The offload write data operation described by this structure is associated with a token representation of data (ROD).


## -struct-fields




### -field WriteUsingTokenDataLength

The length of this structure beginning with the <i>Immediate</i> parameter and include all of the elements of the <b>BlockDeviceRangeDescriptor</b> array.


### -field Immediate

If set, the status of the WRITE USING TOKEN command is returned immediately after receipt and validation of the token ROD and range descriptors. Otherwise, status is returned after all command processing is complete.


### -field Reserved1

Reserved bits.


### -field Reserved2

Reserved.


### -field BlockOffsetIntoToken

The offset, in logical blocks,  in the ROD for <b>Token</b> indicating the start of the source data for the offload write data operation.


### -field Token

A token created by a previous the POPULATE TOKEN command operation.


### -field Reserved3

Reserved.


### -field BlockDeviceRangeDescriptorListLength

The length, in bytes, for all  of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-block_device_range_descriptor">BLOCK_DEVICE_RANGE_DESCRIPTOR</a> structures in the <b>BlockDeviceRangeDescriptor</b> array.


### -field BlockDeviceRangeDescriptor

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-block_device_range_descriptor">BLOCK_DEVICE_RANGE_DESCRIPTOR</a> structures which describe the destination data blocks for the offload write data transfer.


## -remarks



All multibyte values are in big endian format. Prior to setting, these values must be converted from the endian format of the current platform.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-block_device_range_descriptor">BLOCK_DEVICE_RANGE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-populate_token_header">POPULATE_TOKEN_HEADER</a>
 

 

