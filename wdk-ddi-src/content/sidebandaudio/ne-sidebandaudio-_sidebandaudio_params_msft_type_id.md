---
UID: NE:sidebandaudio._SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID
title: _SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID (sidebandaudio.h)
description: "Parameters defined for SIDEBANDAUDIO_PARAMS_SET_STANDARD - Microsoft Type IDs"
ms.date: 07/11/2023
keywords: ["SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID enumeration"]
ms.keywords: _SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID, SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID,
req.header: sidebandaudio.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID
targetos: Windows
tech.root: audio
ms.custom: RS5
f1_keywords:
 - _SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID
 - sidebandaudio/_SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID
 - SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID
 - sidebandaudio/SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - _SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID
 - SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID
---

# _SIDEBANDAUDIO_PARAMS_MSFT_TYPE_ID enumeration

## -description

Parameters defined for SIDEBANDAUDIO_PARAMS_SET_STANDARD - Microsoft Type IDs

## -enum-fields

### -field SBAUD_PARAMS_TYPE_RESERVED

The reserved type parameter set.

## -remarks

For the Microsoft sideband standard set of parameters, the following GUID is defined.

```cpp
// {BF34616B-8265-4D70-ADB2-91B350CCD5D2}
DEFINE_GUID(SIDEBANDAUDIO_PARAMS_SET_STANDARD,
    0xbf34616b, 0x8265, 0x4d70, 0xad, 0xb2, 0x91, 0xb3, 0x50, 0xcc, 0xd5, 0xd2);
```

## -requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sidebandaudio.h |

## -see-also

[sidebandaudio.h](index.md)
