---
UID: NF:sensorsutils.MILLISECONDS_TO_100NANOSECONDS
title: MILLISECONDS_TO_100NANOSECONDS macro (sensorsutils.h)
description: This macro converts time, in milliseconds, to 100 nanosecond units.
ms.date: 01/10/2022
keywords: ["MILLISECONDS_TO_100NANOSECONDS macro"]
tech.root: sensors
ms.keywords: MILLISECONDS_TO_100NANOSECONDS
req.header: sensorsutils.h
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
f1_keywords:
 - MILLISECONDS_TO_100NANOSECONDS
 - sensorsutils/MILLISECONDS_TO_100NANOSECONDS
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - sensorsutils.h
api_name:
 - MILLISECONDS_TO_100NANOSECONDS
product:
 - Windows
---

# MILLISECONDS_TO_100NANOSECONDS macro

## -description

This macro converts time, in milliseconds, to 100 nanosecond units.

## -syntax

```cpp
#define MILLISECONDS_TO_100NANOSECONDS(durationMs) ((durationMs) * 1000 * 10)
```

## -parameters

### -param durationMs

The duration in milliseconds to convert to 100 nanosecond units.

## -remarks

Returns a ULONGLONG that represents a time length in nanoseconds.

## -see-also

- [MILLISECONDS_FROM_100NANOSECONDS](nf-sensorsutils-milliseconds_from_100nanoseconds.md)
