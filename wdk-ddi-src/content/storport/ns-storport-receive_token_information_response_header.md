---
UID: NS:storport.__unnamed_struct_28
title: RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER (storport.h)
description: The RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure (storport.h) contains a token that is created as a representation of data (ROD).
old-location: storage\receive_token_information_response_header.htm
tech.root: storage
ms.date: 05/13/2021
keywords: ["RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure"]
ms.keywords: "*PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure pointer [Storage Devices], RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure [Storage Devices], scsi/PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, scsi/RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, storage.receive_token_information_response_header"
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
req.typenames: RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, *PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
f1_keywords:
 - PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
 - storport/PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
 - RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
 - storport/RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
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

# RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure (storport.h)


## -description

A token, created as a representation of data (ROD), for an offload read data operation is returned in a <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure.

## -struct-fields

### -field TokenDescriptorsLength

The length, in bytes, of the <b>TokenDescriptor</b> member.

### -field TokenDescriptor

The data containing a token created as the offload read ROD.

## -remarks

The <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure is included with a <a href="/windows-hardware/drivers/ddi/storport/ns-storport-receive_token_information_header">RECEIVE_TOKEN_INFORMATION_HEADER</a>structure  as a response to a POPULATE TOKEN command. The <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure follows the <b>SenseData</b> member of <b>RECEIVE_TOKEN_INFORMATION_HEADER</b>.

All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.

## -see-also

<a href="/windows-hardware/drivers/ddi/storport/ns-storport-populate_token_header">POPULATE_TOKEN_HEADER</a>



<a href="/windows-hardware/drivers/ddi/storport/ns-storport-receive_token_information_header">RECEIVE_TOKEN_INFORMATION_HEADER</a>

