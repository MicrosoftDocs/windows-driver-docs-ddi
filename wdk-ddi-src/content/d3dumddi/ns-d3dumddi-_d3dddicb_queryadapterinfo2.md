---
UID: NS:d3dumddi._D3DDDICB_QUERYADAPTERINFO2
title: D3DDDICB_QUERYADAPTERINFO2 (d3dumddi.h)
description: Learn more about the D3DDDICB_QUERYADAPTERINFO2 structure.
ms.date: 02/06/2025
req.header: d3dumddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DDDICB_QUERYADAPTERINFO2
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DDDICB_QUERYADAPTERINFO2
 - d3dumddi/_D3DDDICB_QUERYADAPTERINFO2
 - D3DDDICB_QUERYADAPTERINFO2
 - d3dumddi/D3DDDICB_QUERYADAPTERINFO2
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDICB_QUERYADAPTERINFO2
 - D3DDDICB_QUERYADAPTERINFO2
---

# D3DDDICB_QUERYADAPTERINFO2 structure

## -description

The **D3DDDICB_QUERYADAPTERINFO2** structure describes the graphics adapter.

## -struct-fields

### -field QueryType [in]

A [**D3DDDI_QUERYADAPTERTYPE**](ne-d3dumddi-_d3dddi_queryadaptertype.md) enumeration value that specifies the type of query.

### -field pPrivateDriverData [out]

A pointer to a buffer that receives the requested information. The format of the information is defined by **QueryType**.

### -field PrivateDriverDataSize [in/out]

The size, in bytes, of the buffer that **pPrivateDriverData** points to.

## -see-also

[**D3DDDI_QUERYADAPTERTYPE**](ne-d3dumddi-_d3dddi_queryadaptertype.md)

[**pfnQueryAdapterInfoCb2**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb2.md)
