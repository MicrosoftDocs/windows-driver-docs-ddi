---
UID: NF:amtvuids.OUR_GUID_ENTRY
title: OUR_GUID_ENTRY macro (amtvuids.h)
description: "Learn more about: OUR_GUID_ENTRY macro"
ms.date: 11/17/2020
keywords: ["OUR_GUID_ENTRY macro"]
ms.keywords: OUR_GUID_ENTRY
req.header: amtvuids.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
tech.root: stream
f1_keywords:
 - OUR_GUID_ENTRY
 - amtvuids/OUR_GUID_ENTRY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - amtvuids.h
api_name:
 - OUR_GUID_ENTRY
---

# OUR_GUID_ENTRY macro

## -description

This macro is a wrapper that returns the fields of a DEFINE_GUID structure.

The DEFINE_GUID structure is defined as follows:

```cpp
DEFINE_GUID(name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8);
```

## -parameters

### -param name

Contains the GUID name.

### -param l

Contains an **unsigned integer** value.

### -param w1

Contains an **unsigned short** value.

### -param w2

Contains an **unsigned short** value.

### -param b1

Contains an **unsigned char** value.

### -param b2

Contains an **unsigned char** value.

### -param b3

Contains an **unsigned char** value.

### -param b4

Contains an **unsigned char** value.

### -param b5

Contains an **unsigned char** value.

### -param b6

Contains an **unsigned char** value.

### -param b7

Contains an **unsigned char** value.

### -param b8

Contains an **unsigned char** value.

## -remarks

## -see-also
