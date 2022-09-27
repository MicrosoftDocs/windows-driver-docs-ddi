---
UID: NS:d3dkmthk._D3DKMT_ENUMADAPTERS2
title: D3DKMT_ENUMADAPTERS2 (d3dkmthk.h)
description: Learn more about the D3DKMTEnumAdapters2 structure.
ms.date: 08/30/2022
keywords: ["D3DKMT_ENUMADAPTERS2 structure"]
ms.keywords: _D3DKMT_ENUMADAPTERS2, D3DKMT_ENUMADAPTERS2,
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_ENUMADAPTERS2
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_ENUMADAPTERS2
 - d3dkmthk/_D3DKMT_ENUMADAPTERS2
 - D3DKMT_ENUMADAPTERS2
 - d3dkmthk/D3DKMT_ENUMADAPTERS2
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_ENUMADAPTERS2
 - D3DKMT_ENUMADAPTERS2
dev_langs:
 - c++
---

# D3DKMT_ENUMADAPTERS2 structure

## -description

The **D3DKMT_ENUMADAPTERS2** structure is a parameter passed to [**D3DKMTEnumAdapters2**](nf-d3dkmthk-d3dkmtenumadapters2.md) to acquire information about adapters on the system.

## -struct-fields

### -field NumAdapters

[in, out] The number of adapters.

### -field pAdapters

[out, optional] Pointer to an array of [**D3DKMT_ADAPTERINFO**](ns-d3dkmthk-_d3dkmt_adapterinfo.md) structures in which to receive information for each adapter.

## -remarks

## -see-also

- [D3DKMT_ADAPTERINFO](ns-d3dkmthk-_d3dkmt_adapterinfo.md)
- [D3DKMTEnumAdapters2](nf-d3dkmthk-d3dkmtenumadapters2.md)
- [PFND3DKMT_ENUMADAPTERS2](nc-d3dkmthk-pfnd3dkmt_enumadapters2.md)

