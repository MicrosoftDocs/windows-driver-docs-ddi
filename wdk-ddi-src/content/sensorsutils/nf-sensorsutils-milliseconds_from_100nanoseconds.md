---
UID: NF:sensorsutils.MILLISECONDS_FROM_100NANOSECONDS
title: MILLISECONDS_FROM_100NANOSECONDS macro (sensorsutils.h)
description: This macro converts time, provided as 100 nanosecond units, to milliseconds.
ms.date: 01/10/2022
keywords: ["MILLISECONDS_FROM_100NANOSECONDS macro"]
tech.root: sensors
ms.keywords: MILLISECONDS_FROM_100NANOSECONDS
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
 - MILLISECONDS_FROM_100NANOSECONDS
 - sensorsutils/MILLISECONDS_FROM_100NANOSECONDS
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - sensorsutils.h
api_name:
 - MILLISECONDS_FROM_100NANOSECONDS
product:
 - Windows
---

# MILLISECONDS_FROM_100NANOSECONDS macro

## -description

This macro converts time in 100 nanosecond units, to milliseconds.

## -syntax

```cpp
#define MILLISECONDS_FROM_100NANOSECONDS(durationNanoS) ((durationNanoS) / (1000 * 10))
```

## -parameters

### -param durationNanoS

The duration in 100 nanosecond units to convert to milliseconds.

## -remarks

Gets a LONGLONG that represents a time length in milliseconds.

## -see-also

- [MILLISECONDS_TO_100NANOSECONDS](nf-sensorsutils-milliseconds_to_100nanoseconds.md)
