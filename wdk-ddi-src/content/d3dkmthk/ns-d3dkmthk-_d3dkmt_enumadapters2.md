---
UID: NS:d3dkmthk._D3DKMT_ENUMADAPTERS2
title: _D3DKMT_ENUMADAPTERS2 (d3dkmthk.h)
description: Supplies information for enumerating all graphics adapters on the system.
ms.assetid: a8b97771-732a-4ce3-bf08-31dd1c3a4d91
ms.date: 11/21/2018
f1_keywords:
 - "d3dkmthk/_D3DKMT_ENUMADAPTERS2"
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dkmthk.h
api_name: 
- _D3DKMT_ENUMADAPTERS2
product:
- Windows
targetos: Windows
ms.custom: RS5
dev_langs:
 - c++
tech.root: display
---

# _D3DKMT_ENUMADAPTERS2 structure

## -description

Supplies information about adapters on the system.

## -struct-fields

### -field NumAdapters
*\_Inout\_* *ULONG NumAdapters*

The number of adapters.

On input, NumAdapters specifies how many adapters can be returned in the empty pAdapters array.
After a successful return when pAdapters is non-null, NumAdapters contains how many adapters were returned in the pAdapters array.
After a failed return when pAdapters is non-null, NumAdapters is undefined.
After a successful return when pAdapters is null, NumAdapters contains the maximum supported adapter count.

### -field pAdapters
*\_Out\_opt\_* *[D3DKMT_ADAPTERINFO](ns-d3dkmthk-_d3dkmt_adapterinfo.md)* * *pAdapters*
 
An optional array to receive information for each adapter.

## -remarks

## -see-also
- [D3DKMT_ADAPTERINFO](ns-d3dkmthk-_d3dkmt_adapterinfo.md)
- [D3DKMTEnumAdapters2](nf-d3dkmthk-d3dkmtenumadapters2.md)
- [PFND3DKMT_ENUMADAPTERS2](nc-d3dkmthk-pfnd3dkmt_enumadapters2.md)
