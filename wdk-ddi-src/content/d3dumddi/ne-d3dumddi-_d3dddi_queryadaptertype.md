---
UID: NE:d3dumddi._D3DDDI_QUERYADAPTERTYPE
title: D3DDDI_QUERYADAPTERTYPE (d3dumddi.h)
description: Learn more about the D3DDDI_QUERYADAPTERTYPE enumeration.
ms.date: 02/06/2025
req.header: d3dumddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3DDDI_QUERYADAPTERTYPE
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DDDI_QUERYADAPTERTYPE
 - d3dumddi/_D3DDDI_QUERYADAPTERTYPE
 - D3DDDI_QUERYADAPTERTYPE
 - d3dumddi/D3DDDI_QUERYADAPTERTYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDI_QUERYADAPTERTYPE
 - D3DDDI_QUERYADAPTERTYPE
---

# D3DDDI_QUERYADAPTERTYPE enumeration

## -description

The **D3DDDI_QUERYADAPTERTYPE** enumeration specifies the type of query for [**pfnQueryAdapterInfoCb2**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb2.md).

## -enum-fields

### -field D3DDDI_QUERYADAPTERTYPE_DRIVERPRIVATE

Query the driver's private data.

### -field D3DDDI_QUERYADAPTERTYPE_QUERYREGISTRY

Query for information stored in the registry.

### -field D3DDDI_QUERYADAPTERTYPE_APPLICATIONSPECIFICDRIVERBLOB

Query for an application-specific driver blob.

## -see-also

[**D3DDDICB_QUERYADAPTERINFO2**](ns-d3dumddi-_d3dddicb_queryadapterinfo2.md)

[**pfnQueryAdapterInfoCb2**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb2.md)
