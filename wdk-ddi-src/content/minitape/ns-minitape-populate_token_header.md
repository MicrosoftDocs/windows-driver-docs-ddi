---
UID: NS:minitape.__unnamed_struct_16
title: POPULATE_TOKEN_HEADER (minitape.h)
description: A populate token parameter list starts with a POPULATE_TOKEN_HEADER structure. This is the header for the parameters in a command data block (CDB) of the POPULATE TOKEN command.
old-location: storage\populate_token_header.htm
tech.root: storage
ms.assetid: 897C74A3-041D-487E-8891-7161B76ABAA1
ms.date: 03/29/2018
keywords: ["POPULATE_TOKEN_HEADER structure"]
ms.keywords: "*PPOPULATE_TOKEN_HEADER, POPULATE_TOKEN_HEADER, POPULATE_TOKEN_HEADER structure [Storage Devices], PPOPULATE_TOKEN_HEADER, PPOPULATE_TOKEN_HEADER structure pointer [Storage Devices], scsi/POPULATE_TOKEN_HEADER, scsi/PPOPULATE_TOKEN_HEADER, storage.populate_token_header"
req.header: minitape.h
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
req.typenames: POPULATE_TOKEN_HEADER, *PPOPULATE_TOKEN_HEADER
f1_keywords:
 - PPOPULATE_TOKEN_HEADER
 - minitape/PPOPULATE_TOKEN_HEADER
 - POPULATE_TOKEN_HEADER
 - minitape/POPULATE_TOKEN_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - POPULATE_TOKEN_HEADER
---

# POPULATE_TOKEN_HEADER structure (minitape.h)


## -description

A populate token parameter list starts with a <b>POPULATE_TOKEN_HEADER</b> structure. This is the header for the parameters in a command data block (CDB) of the  POPULATE TOKEN command.

## -struct-fields

### -field PopulateTokenDataLength

The length of this structure beginning with the <i>Immediate</i> parameter and include all of the elements of the <b>BlockDeviceRangeDescriptor</b> array.

### -field Immediate

If set, the status of the POPULATE TOKEN command is returned immediately after receipt and validation of the range descriptors. Otherwise, status is returned after all command processing is complete.

### -field Reserved1

Reserved bits.

### -field Reserved2

Reserved.

### -field InactivityTimeout

The timeout duration for which the copy provider waits for the next command using the token created for this representation of data (ROD). The validity of the token created  for the ROD described by this structure expires at this timeout value.

### -field Reserved3

Reserved.

### -field BlockDeviceRangeDescriptorListLength

The length, in bytes, for all  of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-block_device_range_descriptor">BLOCK_DEVICE_RANGE_DESCRIPTOR</a> structures in the <b>BlockDeviceRangeDescriptor</b> array.

### -field BlockDeviceRangeDescriptor

An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-block_device_range_descriptor">BLOCK_DEVICE_RANGE_DESCRIPTOR</a> structures which describe the logical blocks representing the file being read from the LUN.

## -remarks

The <b>POPULATE_TOKEN_HEADER</b> structure contains a series of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-block_device_range_descriptor">BLOCK_DEVICE_RANGE_DESCRIPTOR</a> structures which describe the token ROD.

All multibyte values are in big endian format. Prior to setting, these values must be converted from the endian format of the current platform.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsi/ns-scsi-block_device_range_descriptor">BLOCK_DEVICE_RANGE_DESCRIPTOR</a>

