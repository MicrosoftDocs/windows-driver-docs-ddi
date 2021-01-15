---
UID: NS:d3dkmthk._D3DKMT_ENUMADAPTERS3
title: _D3DKMT_ENUMADAPTERS3 (d3dkmthk.h)
description: Supplies information for enumerating all graphics adapters on the system.
ms.date: 03/24/2020
keywords: ["D3DKMT_ENUMADAPTERS3 structure"]
ms.keywords: _D3DKMT_ENUMADAPTERS3, D3DKMT_ENUMADAPTERS3,
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_ENUMADAPTERS3
targetos: Windows
ms.custom: 
tech.root: display
f1_keywords:
 - _D3DKMT_ENUMADAPTERS3
 - d3dkmthk/_D3DKMT_ENUMADAPTERS3
 - D3DKMT_ENUMADAPTERS3
 - d3dkmthk/D3DKMT_ENUMADAPTERS3
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_ENUMADAPTERS3
 - D3DKMT_ENUMADAPTERS3
dev_langs:
 - c++
---

# D3DKMT_ENUMADAPTERS3 structure


## -description

Supplies information about adapters on the system.

## -struct-fields

### -field Filter

[in] A **D3DKMT_ENUMADAPTERS_FILTER** union containing filter flags for the enumeration. The struct in **Filter** can be a bitwise OR of the following values. See Remarks for more information.

| Value | Meaning |
| ----- | ------- |
| IncludeComputeOnly | When set, enumerate ComputeOnly adapters. |
| IncludeDisplayOnly | When set, enumerate DisplayOnly adapters. |
| Reserved           | Reserved; do not use.                     |

### -field NumAdapters

[in/out] The number of adapters.

On input, **NumAdapters** specifies how many adapters can be returned in the empty **pAdapters** array. Possible return values for **NumAdapters** are:

- On successful return when **pAdapters** is non-null, **NumAdapters** contains how many adapters were returned in the **pAdapters** array.
- On successful return when **pAdapters** is null, **NumAdapters** contains the maximum supported adapter count.
- On failed return when **pAdapters** is non-null, **NumAdapters** is undefined.

### -field pAdapters

[out] An optional array of [**D3DKMT_ADAPTERINFO**](ns-d3dkmthk-_d3dkmt_adapterinfo.md) structures in which to receive information for each adapter.

## -remarks

Adapters will still be enumerated if no flags are set in **Filter**, but [**D3DKMTEnumAdapters3**](nf-d3dkmthk-d3dkmtenumadapters3.md) will enumerate fewer adapters than [**D3DKMTEnumAdapters2**](nf-d3dkmthk-d3dkmtenumadapters2.md). Specifically, **D3DKMTEnumAdapters3** will:

- Leave out ComputeOnly adapters from the default enumeration, to avoid breaking applications.
- Leave out DisplayOnly adapters from the default enumeration.

## -see-also

[**D3DKMT_ADAPTERINFO**](ns-d3dkmthk-_d3dkmt_adapterinfo.md)

[**D3DKMTEnumAdapters3**](nf-d3dkmthk-d3dkmtenumadapters3.md)

[**PFND3DKMT_ENUMADAPTERS3**](nc-d3dkmthk-pfnd3dkmt_enumadapters3.md)

