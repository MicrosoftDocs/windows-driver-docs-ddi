---
UID: NE:rxcontx.RX_CONTEXT_CREATE_FLAGS
tech.root: ifsk
title: RX_CONTEXT_CREATE_FLAGS
ms.date: 10/29/2024
targetos: Windows
description: Learn more about the RX_CONTEXT_CREATE_FLAGS enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: rxcontx.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: true
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - rxcontx.h
api_name:
 - RX_CONTEXT_CREATE_FLAGS
f1_keywords:
 - RX_CONTEXT_CREATE_FLAGS
 - rxcontx/RX_CONTEXT_CREATE_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - RX_CONTEXT_CREATE_FLAGS
---

## -description

**RX_CONTENT_CREATE_FLAGS** specifies flags set by RDBSS and passed to operations sent to the network mini-redirector during the creation of a context.

## -enum-fields

### -field RX_CONTEXT_CREATE_FLAG_UNC_NAME:0x1

The user presented a UNC path name.

### -field RX_CONTEXT_CREATE_FLAG_STRIPPED_TRAILING_BACKSLASH:0x2

The trailing backslash was stripped from the path name.

### -field RX_CONTEXT_CREATE_FLAG_ADDEDBACKSLASH:0x4

A backslash was added to the path name.

### -field RX_CONTEXT_CREATE_FLAG_REPARSE:0x8

A reparse operation is needed.

### -field RX_CONTEXT_CREATE_FLAG_SPECIAL_PATH:0x10

Designates the path as special.

## -see-also

[**RxCreateRxContext**](nf-rxcontx-rxcreaterxcontext.md)

[**RX_CONTEXT**](ns-rxcontx-_rx_context.md)
