---
UID: NS:ntifs._SEC_CHANNEL_BINDINGS_RESULT
tech.root: ifsk
title: SEC_CHANNEL_BINDINGS_RESULT
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the SEC_CHANNEL_BINDINGS_RESULT structure.
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
req.typenames: SEC_CHANNEL_BINDINGS_RESULT, *PSEC_CHANNEL_BINDINGS_RESULT
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
 - _SEC_CHANNEL_BINDINGS_RESULT
 - PSEC_CHANNEL_BINDINGS_RESULT
 - SEC_CHANNEL_BINDINGS_RESULT
f1_keywords:
 - _SEC_CHANNEL_BINDINGS_RESULT
 - ntifs/_SEC_CHANNEL_BINDINGS_RESULT
 - PSEC_CHANNEL_BINDINGS_RESULT
 - ntifs/PSEC_CHANNEL_BINDINGS_RESULT
 - SEC_CHANNEL_BINDINGS_RESULT
 - ntifs/SEC_CHANNEL_BINDINGS_RESULT
dev_langs:
 - c++
helpviewer_keywords:
 - _SEC_CHANNEL_BINDINGS_RESULT
---

## -description

The **SEC_CHANNEL_BINDINGS_RESULT** structure is used to represent the outcome of channel bindings verification in secure communication protocols.

## -struct-fields

### -field flags

Flags related to the channel bindings result. This field is a bitwise OR of the following values:

| Flag | Description |
| ---- | ----------- |
| SEC_CHANNEL_BINDINGS_RESULT_CLIENT_SUPPORT (0x1) | Indicates that the authentication package requires client versions to support channel bindings. |
| SEC_CHANNEL_BINDINGS_RESULT_ABSENT (0x2) | Indicates that the channel bindings are either omitted or consist entirely of zeroes. |
| SEC_CHANNEL_BINDINGS_RESULT_NOTVALID_MISMATCH (0x4) | Indicates that the channel binding hash was incorrect, suggesting a mismatch between expected and actual bindings. |
| SEC_CHANNEL_BINDINGS_RESULT_NOTVALID_MISSING (0x8) | Indicates that missing channel bindings are not allowed for this client, and their absence is considered invalid. |
| SEC_CHANNEL_BINDINGS_RESULT_VALID_MATCHED (0x10) | Indicates that the client and server channel bindings match, confirming the validity of the bindings. |
| SEC_CHANNEL_BINDINGS_RESULT_VALID_PROXY (0x20) | Indicates that the ASC_REQ_PROXY_BINDINGS flag required the client to provide a binding, and this requirement was met. |
| SEC_CHANNEL_BINDINGS_RESULT_VALID_MISSING (0x40) | Indicates that the client is permitted to have missing bindings, as allowed by the ASC_REQ_ALLOW_MISSING_BINDINGS flag. |
