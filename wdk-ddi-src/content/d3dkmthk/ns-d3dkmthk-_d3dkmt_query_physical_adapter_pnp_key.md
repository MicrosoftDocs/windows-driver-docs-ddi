---
UID: NS:d3dkmthk._D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
title: D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY (d3dkmthk.h)
description: Learn more about the D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY structure.
ms.date: 02/06/2025
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
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
tech.root: display
req.typenames: D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
f1_keywords:
 - _D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
 - d3dkmthk/_D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
 - D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
 - d3dkmthk/D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
 - D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY
---

# D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY structure

## -description

The **D3DKMT_QUERY_PHYSICAL_ADAPTER_PNP_KEY** structure holds information to query the physical adapter PNP key.

## -struct-fields

### -field PhysicalAdapterIndex

The physical adapter index in the LDA (linked display adapter) chain.

### -field PnPKeyType

A [**D3DKMT_PNP_KEY_TYPE**](ne-d3dkmthk-_d3dkmt_pnp_key_type.md) enumeration value that specifies the type of the PNP key being queried.

### -field pDest

Pointer to a buffer that receives the requested PnP key as a wide-character string.

### -field pCchDest

Pointer to a variable that specifies the size of the **pDest** buffer, in characters. On input, it should contain the maximum number of characters that can be stored in the buffer. On output, it is updated to reflect the actual number of characters written to **pDest**, including the null terminator.

## -see-also

[**D3DKMT_PNP_KEY_TYPE**](ne-d3dkmthk-_d3dkmt_pnp_key_type.md)

[**D3DKMTQueryAdapterInfo**](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)

