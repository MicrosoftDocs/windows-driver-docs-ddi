---
UID: NS:minitape.RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
title: RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER (minitape.h)
description: The RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure (minitape.h) contains a token that is created as a representation of data (ROD).
tech.root: storage
ms.date: 09/23/2022
keywords: ["RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure"]
ms.keywords: "*PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure pointer [Storage Devices], RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure [Storage Devices], scsi/PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, scsi/RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, storage.receive_token_information_response_header"
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
req.typenames: RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, *PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
f1_keywords:
 - PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
 - minitape/PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
 - RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
 - minitape/RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
 - RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
---

## -description

A token, created as a representation of data (ROD), for an offload read data operation is returned in a **RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER** structure.

## -struct-fields

### -field TokenDescriptorsLength

The length, in bytes, of the **TokenDescriptor** member.

### -field TokenDescriptor

The data containing a token created as the offload read ROD.

## -remarks

The **RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER** structure is included with a [**RECEIVE_TOKEN_INFORMATION_HEADER**](../storport/ns-storport-receive_token_information_header.md)structure  as a response to a POPULATE TOKEN command. The **RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER** structure follows the **SenseData** member of **RECEIVE_TOKEN_INFORMATION_HEADER**.

All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.

## -see-also

[**POPULATE_TOKEN_HEADER**](../storport/ns-storport-populate_token_header.md)

[**RECEIVE_TOKEN_INFORMATION_HEADER**](../storport/ns-storport-receive_token_information_header.md)

