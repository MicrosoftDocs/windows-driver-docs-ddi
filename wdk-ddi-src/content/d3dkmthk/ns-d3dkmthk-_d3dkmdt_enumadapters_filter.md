---
UID: NS:d3dkmthk._D3DKMDT_ENUMADAPTERS_FILTER
title: D3DKMDT_ENUMADAPTERS_FILTER (d3dkmthk.h)
description: The D3DKMDT_ENUMADAPTERS_FILTER union identifies attributes of a display mode.
old-location: display\d3dkmdt_enumadapters_filter.htm
ms.assetid: 2e87e5ea-95bf-4161-8e23-a3570f87bc6e
ms.date: 03/24/2020
keywords: ["_D3DKMDT_ENUMADAPTERS_FILTER union"]
ms.keywords: D3DKMDT_ENUMADAPTERS_FILTER, D3DKMDT_ENUMADAPTERS_FILTER union [Display Devices], _D3DKMDT_ENUMADAPTERS_FILTER, d3dkmthk/D3DKMDT_ENUMADAPTERS_FILTER
f1_keywords:
 - "d3dkmthk/D3DKMDT_ENUMADAPTERS_FILTER"
 - "D3DKMDT_ENUMADAPTERS_FILTER"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 2004
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMDT_ENUMADAPTERS_FILTER
targetos: Windows
tech.root: display
req.typenames: D3DKMDT_ENUMADAPTERS_FILTER
---

# _D3DKMDT_ENUMADAPTERS_FILTER union

## -description

The **D3DKMDT_ENUMADAPTERS_FILTER** union contains filter flags for adapter enumeration.

## -syntax

```cpp
typedef union _D3DKMT_ENUMADAPTERS_FILTER
{
    struct
    {
        ULONGLONG IncludeComputeOnly            : 1;
        ULONGLONG IncludeDisplayOnly            : 1;
        ULONGLONG Reserved                      : 62;
    };
    ULONGLONG Value;
} D3DKMT_ENUMADAPTERS_FILTER;
```

## -struct-fields

### -field

Filter flags for the enumeration. Can be a bitwise OR of the following values:

| Value | Meaning |
| ----- | ------- |
| IncludeComputeOnly | When set, enumerate ComputeOnly adapters. |
| IncludeDisplayOnly | When set, enumerate DisplayOnly adapters. |
| Reserved           | Reserved; do not use.                     |

### -field Value

Value used to operate over the members collectively.

## -remarks

**D3DKMDT_ENUMADAPTERS_FILTER** is a member of the [**D3DKMT_ENUMADAPTERS3**](ns-d3dkmthk-_d3dkmt_enumadapters3.md) structure, which is passed as a parameter to [**D3DKMTEnumAdapters3**](nf-d3dkmthk-d3dkmtenumadapters3.md).

Setting none of these flags will still enumerate adapters, but [**D3DKMTEnumAdapters3**](nf-d3dkmthk-d3dkmtenumadapters3.md) will enumerate fewer adapters than [**D3DKMTEnumAdapters2**](nf-d3dkmthk-d3dkmtenumadapters2.md). Specifically:

- ComputeOnly adapters are left out of the default enumeration, to avoid breaking applications.
- DisplayOnly adapters are also left out of the default enumeration.

## -see-also

[**D3DKMT_ENUMADAPTERS3**](ns-d3dkmthk-_d3dkmt_enumadapters3.md)

[**D3DKMTEnumAdapters2**](nf-d3dkmthk-d3dkmtenumadapters2.md)

[**D3DKMTEnumAdapters3**](nf-d3dkmthk-d3dkmtenumadapters3.md)
