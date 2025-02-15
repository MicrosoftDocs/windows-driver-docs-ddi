---
UID: NS:ntifs._SEC_CHANNEL_BINDINGS_EX
tech.root: ifsk
title: SEC_CHANNEL_BINDINGS_EX
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the SEC_CHANNEL_BINDINGS_EX structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: SEC_CHANNEL_BINDINGS_EX, *PSEC_CHANNEL_BINDINGS_EX
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _SEC_CHANNEL_BINDINGS_EX
 - PSEC_CHANNEL_BINDINGS_EX
 - SEC_CHANNEL_BINDINGS_EX
f1_keywords:
 - _SEC_CHANNEL_BINDINGS_EX
 - ntifs/_SEC_CHANNEL_BINDINGS_EX
 - PSEC_CHANNEL_BINDINGS_EX
 - ntifs/PSEC_CHANNEL_BINDINGS_EX
 - SEC_CHANNEL_BINDINGS_EX
 - ntifs/SEC_CHANNEL_BINDINGS_EX
dev_langs:
 - c++
helpviewer_keywords:
 - _SEC_CHANNEL_BINDINGS_EX
---

## -description

The **SEC_CHANNEL_BINDINGS_EX** structure is used to provide channel binding information for a security context.

## -struct-fields

### -field magicNumber

Contains SEC_CHANNEL_BINDINGS_VERSION_2. This member ensures that the structure is correctly identified as an extended version, preventing misinterpretation as a standard channel bindings buffer.

### -field flags

Specifies additional options for channel bindings. The following flag is defined.

| Flag | Description |
|------|-------------|
| SEC_CHANNEL_BINDINGS_VALID_FLAGS | Indicates that auditing is required for operations involving these channel bindings. |

### -field cbHeaderLength

Length in bytes of the header portion of the structure.

### -field cbStructureLength

Total length in bytes of the entire structure, including the header and all channel binding data.

### -field dwInitiatorAddrType

Address type of the initiator, indicating the format of the initiator's address.

### -field cbInitiatorLength

Length in bytes of the initiator's address data.

### -field dwInitiatorOffset

Offset in bytes from the start of structure to the initiator's address data.

### -field dwAcceptorAddrType

Address type of the acceptor, indicating the format of the acceptor's address.

### -field cbAcceptorLength

Length in bytes of the acceptor's address data.

### -field dwAcceptorOffset

Offset in bytes from the start of the structure to the acceptor's address data.

### -field cbApplicationDataLength

Length in bytes of the application-specific data.

### -field dwApplicationDataOffset

Offset in bytes from the start of the structure to the application-specific data.
