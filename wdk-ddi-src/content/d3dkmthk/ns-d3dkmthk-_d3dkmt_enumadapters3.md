---
UID: NS:d3dkmthk._D3DKMT_ENUMADAPTERS3
title: _D3DKMT_ENUMADAPTERS3 (d3dkmthk.h)
description: Supplies information for enumerating all graphics adapters on the system.
ms.assetid: 82fbef6f-b3ce-4ab8-b5af-cbb219593d3f
ms.date: 03/24/2020
keywords: ["_D3DKMT_ENUMADAPTERS3 structure"]
f1_keywords:
 - "d3dkmthk/_D3DKMT_ENUMADAPTERS3"
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_ENUMADAPTERS3
product:
- Windows
targetos: Windows
ms.custom:
dev_langs:
 - c++
tech.root: display
---

# D3DKMT_ENUMADAPTERS3 structure

## -description

Supplies information about adapters on the system.

## -struct-fields

### -field Filter

[in] A [**D3DKMT_ENUMADAPTERS_FILTER**](ns-d3dkmthk-_d3dkmdt_enumadapters_filter.md) union containing filter flags for the enumeration.

### -field NumAdapters

[in/out] The number of adapters.

On input, **NumAdapters** specifies how many adapters can be returned in the empty **pAdapters** array. Possible return values for **NumAdapters** are:

- On successful return when **pAdapters** is non-null, **NumAdapters** contains how many adapters were returned in the **pAdapters** array.
- On successful return when **pAdapters** is null, **NumAdapters** contains the maximum supported adapter count.
- On failed return when **pAdapters** is non-null, **NumAdapters** is undefined.

### -field pAdapters

[out] An optional array of [**D3DKMT_ADAPTERINFO**](ns-d3dkmthk-_d3dkmt_adapterinfo.md) structures in which to receive information for each adapter.

## -remarks

## -see-also

[**D3DKMT_ADAPTERINFO**](ns-d3dkmthk-_d3dkmt_adapterinfo.md)

[**D3DKMT_ENUMADAPTERS_FILTER**](ns-d3dkmthk-_d3dkmdt_enumadapters_filter.md)

[**D3DKMTEnumAdapters3**](nf-d3dkmthk-d3dkmtenumadapters3.md)

[**PFND3DKMT_ENUMADAPTERS3**](nc-d3dkmthk-pfnd3dkmt_enumadapters3.md)
