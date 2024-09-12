---
UID: NS:d3dukmdt._D3DDDI_QUERYREGISTRY_FLAGS
title: D3DDDI_QUERYREGISTRY_FLAGS (d3dukmdt.h)
description: Learn about the D3DDDI_QUERYREGISTRY_FLAGS structure.
ms.date: 06/14/2024
keywords: ["D3DDDI_QUERYREGISTRY_FLAGS structure"]
ms.keywords: _D3DDDI_QUERYREGISTRY_FLAGS, D3DDDI_QUERYREGISTRY_FLAGS,
req.header: d3dukmdt.h
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
req.typenames: D3DDDI_QUERYREGISTRY_FLAGS
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DDDI_QUERYREGISTRY_FLAGS
 - d3dukmdt/_D3DDDI_QUERYREGISTRY_FLAGS
 - D3DDDI_QUERYREGISTRY_FLAGS
 - d3dukmdt/D3DDDI_QUERYREGISTRY_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_QUERYREGISTRY_FLAGS
 - D3DDDI_QUERYREGISTRY_FLAGS
---

# D3DDDI_QUERYREGISTRY_FLAGS structure

## -description

These flags control how strings are being retrieved through [**D3DKMTQueryAdapterInfo**](../d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo.md) for **KMTQAITYPE_QUERYREGISTRY**.

## -struct-fields

### -field TranslatePath

When a particular registry key stores a path to another driver file, the caller of QueryAdapterInfo might have that path translated into the path that an isolated processes can access.
Setting **TranslatePath** to 1 indicates the registry key is a string that should be translated, when appropriate.

The registry string must be a full path to a file in the driver store. Translation won't occur when translation isn't needed.

**TranslatePath** must be set to 0 when **D3DDDI_QUERYREGISTRY_DRIVERSTOREPATH** and **D3DDDI_QUERYREGISTRY_DRIVERIMAGEPATH** are used.
However, **D3DDDI_QUERYREGISTRY_DRIVERSTOREPATH** and **D3DDDI_QUERYREGISTRY_DRIVERIMAGEPATH** will always act as-if **TranslatePath** were set to 1.

### -field MutableValue

Reserved. Callers of QueryAdapterInfo must set this value to 0.

### -field Reserved

Reserved. Callers of QueryAdapterInfo must set this value to 0.

### Value

The **Value** field exists to read all these flags in a raw syntax, instead of the named bitfield.

## -see-also

[**D3DDDI_QUERYREGISTRY_INFO**](ns-d3dukmdt-_d3dddi_queryregistry_info.md)
