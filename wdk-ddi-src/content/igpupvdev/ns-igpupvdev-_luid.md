---
UID: NS:igpupvdev._LUID
title: LUID (igpupvdev.h)
description: The locally unique identifier (LUID) is a 64-bit value guaranteed to be unique only on the system on which it was generated.
tech.root: display
ms.date: 02/10/2025
req.header: igpupvdev.h
req.include-header: Fwptypes.h, Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: LUID
f1_keywords:
 - _LUID
 - igpupvdev/_LUID
 - LUID
 - igpupvdev/LUID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - igpupvdev.h
api_name:
 - _LUID
 - LUID
---

# LUID structure

## -description

A LUID (locally unique identifier) is a 64-bit value guaranteed to be unique only on the system on which it was generated. The uniqueness of a LUID is guaranteed only until the system is restarted.

A LUID is not for direct manipulation. Drivers must use support routines and structures to manipulate LUID values.

## -struct-fields

### -field LowPart

Low order bits.

### -field HighPart

High order bits.

## -syntax

```cpp
typedef struct _LUID {
  DWORD LowPart;
  LONG  HighPart;
} LUID, *PLUID;
```
