---
UID: NS:d3dkmthk._D3DKMT_QUERYADAPTERINFO
title: D3DKMT_QUERYADAPTERINFO (d3dkmthk.h)
description: Learn more about the D3DKMT_QUERYADAPTERINFO structure.
ms.date: 02/06/2025
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
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
req.typenames: D3DKMT_QUERYADAPTERINFO
f1_keywords:
 - _D3DKMT_QUERYADAPTERINFO
 - d3dkmthk/_D3DKMT_QUERYADAPTERINFO
 - D3DKMT_QUERYADAPTERINFO
 - d3dkmthk/D3DKMT_QUERYADAPTERINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_QUERYADAPTERINFO
 - D3DKMT_QUERYADAPTERINFO
---

# D3DKMT_QUERYADAPTERINFO structure

## -description

The **D3DKMT_QUERYADAPTERINFO** structure retrieves various information that describes the adapter.

## -struct-fields

### -field hAdapter

[in] A handle to the adapter that information is retrieved about.

### -field Type

[in] A [**KMTQUERYADAPTERINFOTYPE**](ne-d3dkmthk-_kmtqueryadapterinfotype.md) enumeration value that indicates the type of information to retrieve.

### -field pPrivateDriverData

[in/out] Pointer to a memory region that is interpreted based on the value of **Type**.

### -field PrivateDriverDataSize

[in/out] The size, in bytes, of the buffer that **pPrivateDriverData** points to.

## -see-also

[**KMTQUERYADAPTERINFOTYPE**](ne-d3dkmthk-_kmtqueryadapterinfotype.md)

[**D3DKMTQueryAdapterInfo**](nf-d3dkmthk-d3dkmtqueryadapterinfo.md)

[**PFND3DKMT_QUERYADAPTERINFO**](nc-d3dkmthk-pfnd3dkmt_queryadapterinfo.md)
