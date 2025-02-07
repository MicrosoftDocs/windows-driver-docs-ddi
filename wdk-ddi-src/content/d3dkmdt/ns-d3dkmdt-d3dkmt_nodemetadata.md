---
UID: NS:d3dkmdt._D3DKMT_NODEMETADATA
tech.root: display
title: D3DKMT_NODEMETADATA
ms.date: 01/21/2025
targetos: Windows
description: Learn more about the D3DKMT_NODEMETADATA structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmdt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DKMT_NODEMETADATA
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _D3DKMT_NODEMETADATA
 - D3DKMT_NODEMETADATA
f1_keywords:
 - _D3DKMT_NODEMETADATA
 - d3dkmdt/_D3DKMT_NODEMETADATA
 - D3DKMT_NODEMETADATA
 - d3dkmdt/D3DKMT_NODEMETADATA
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DKMT_NODEMETADATA
---

## -description

The **D3DKMT_NODEMETADATA** structure describes the metadata for a node.

## -struct-fields

### -field NodeOrdinalAndAdapterIndex

[in] Identifies the node ordinal and adapter index. The high word is the physical adapter index, and the low word is the node ordinal.

### -field NodeData

[out] A [**DXGK_NODEMETADATA**](../d3dkmdt/ns-d3dkmdt-_dxgk_nodemetadata.md) structure in which the display miniport driver writes the metadata for the node.

## -see-also

[**D3DKMTQueryAdapterInfo**](../d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo.md)

[**DXGK_NODEMETADATA**](../d3dkmdt/ns-d3dkmdt-_dxgk_nodemetadata.md)
