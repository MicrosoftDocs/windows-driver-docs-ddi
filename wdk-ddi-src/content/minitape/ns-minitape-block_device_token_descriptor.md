---
UID: NS:minitape.__unnamed_struct_29
title: BLOCK_DEVICE_TOKEN_DESCRIPTOR (minitape.h)
description: The BLOCK_DEVICE_TOKEN_DESCRIPTOR structure (minitape.h) contains the token returned from the POPULATE TOKEN command for an offload read data operation.
tech.root: storage
ms.date: 09/23/2022
keywords: ["BLOCK_DEVICE_TOKEN_DESCRIPTOR structure"]
ms.keywords: "*PBLOCK_DEVICE_TOKEN_DESCRIPTOR, BLOCK_DEVICE_TOKEN_DESCRIPTOR, BLOCK_DEVICE_TOKEN_DESCRIPTOR structure [Storage Devices], PBLOCK_DEVICE_TOKEN_DESCRIPTOR, PBLOCK_DEVICE_TOKEN_DESCRIPTOR structure pointer [Storage Devices], scsi/BLOCK_DEVICE_TOKEN_DESCRIPTOR, scsi/PBLOCK_DEVICE_TOKEN_DESCRIPTOR, storage.block_device_token_descriptor"
req.header: minitape.h
req.include-header: Scsi.h, Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.typenames: BLOCK_DEVICE_TOKEN_DESCRIPTOR, *PBLOCK_DEVICE_TOKEN_DESCRIPTOR
f1_keywords:
 - PBLOCK_DEVICE_TOKEN_DESCRIPTOR
 - minitape/PBLOCK_DEVICE_TOKEN_DESCRIPTOR
 - BLOCK_DEVICE_TOKEN_DESCRIPTOR
 - minitape/BLOCK_DEVICE_TOKEN_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - PBLOCK_DEVICE_TOKEN_DESCRIPTOR
 - BLOCK_DEVICE_TOKEN_DESCRIPTOR
---

## -description

**BLOCK_DEVICE_TOKEN_DESCRIPTOR** contains the token returned from a the POPULATE TOKEN command for an offload read data operation. The token information is included as part of the [**RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER**](/windows-hardware/drivers/ddi/minitape/ns-minitape-receive_token_information_response_header) structure.

## -struct-fields

### -field TokenIdentifier

An identifier value assigned by the copy provider to provide uniqueness to **Token** while the value of **Token** is valid. This member is reserved for system use and must not be modified.

### -field Token

A data value defining a token as a point-in-time representation of data (ROD) for an offload read data operation. **Token** is an opaque value and must be used unmodified in offload write data operations.

## -see-also

[**RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER**](/windows-hardware/drivers/ddi/minitape/ns-minitape-receive_token_information_response_header)
