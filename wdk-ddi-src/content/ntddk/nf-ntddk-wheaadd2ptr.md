---
UID: NF:ntddk.WheaAdd2Ptr
tech.root: kernel
title: WheaAdd2Ptr (ntddk.h)
ms.date: 03/25/2022
targetos: Windows
description: This topic describes the WheaAdd2Ptr macro.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.idl: 
req.include-header: Ntddk.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WheaAdd2Ptr
f1_keywords:
 - WheaAdd2Ptr
 - ntddk/WheaAdd2Ptr
dev_langs:
 - c++
helpviewer_keywords:
 - WheaAdd2Ptr
---

## -description

This topic describes the **WheaAdd2Ptr** macro.

## -parameters

### -param P

A pointer to an error record.

### -param I

A pointer to a descriptor.

## -remarks

The macro is defined as follows:

```cpp
#define WheaAdd2Ptr(P,I) ((PVOID)((PUCHAR)(P) + (I)))
```

## -see-also
