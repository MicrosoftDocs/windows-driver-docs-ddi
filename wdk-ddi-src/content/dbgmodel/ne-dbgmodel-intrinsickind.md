---
UID: NE:dbgmodel.IntrinsicKind
title: IntrinsicKind
author: windows-driver-content
description: Defines the kind of an intrinsic (basic) type.  This is distinct from the variant type which carries the type.
ms.assetid: c1a4180d-3606-46d5-811c-ee0e7cd5a96c
ms.date: 07/16/2018
ms.topic: enum
ms.keywords: IntrinsicKind, , 
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	dbgmodel.h
api_name: 
-	IntrinsicKind
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IntrinsicKind enumeration

## -description

Defines the kind of an intrinsic (basic) type.  This is distinct from the variant type which carries the type.


## -enum-fields

### -field IntrinsicVoid 
void

### -field IntrinsicBool 
bool

### -field IntrinsicChar 
char

### -field IntrinsicWChar 
wchar_t

### -field IntrinsicInt 
signed int (of some size -- not necessarily 4 bytes)

### -field IntrinsicUInt 
unsigned int (of some size -- not necessarily 4 bytes)

### -field IntrinsicLong 
long (of some size)

### -field IntrinsicULong 
unsigned long (of some size)

### -field IntrinsicFloat 
floating point (of some size -- not necessarily 4 bytes)

### -field IntrinsicHRESULT 
HRESULT

### -field IntrinsicChar16 
char16_t

### -field IntrinsicChar32 
char32_t

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
