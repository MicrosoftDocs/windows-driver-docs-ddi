---
UID: NS:d3dukmdt._D3DDDI_QUERYREGISTRY_FLAGS
title: _D3DDDI_QUERYREGISTRY_FLAGS (d3dukmdt.h)
description: Contains information to query for registry flags.
ms.assetid: 9dabfa1e-4574-4a82-a7c9-f44d5012dcbb
ms.date: 11/21/2018
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
product:
 - Windows
---

# _D3DDDI_QUERYREGISTRY_FLAGS structure


## -description

These flags control how strings are being retrieved through QueryAdapterInfo for **KMTQAITYPE_QUERYREGISTRY**.

## -struct-fields

## -see-also

### TranslatePath
*UINT TranslatePath : 1*

When a particular registry key stores a path to another driver file, the caller of QueryAdapterInfo may have that path translated into the path that an isolated processes can access.
Setting **TranslatePath** to 1 indicates the registry key is a string that should be translated, when appropriate.
The registry string must be a full path to a file in the driver store, and translation will not occur when translation is not needed.

**TranslatePath** must be set to 0 when **D3DDDI_QUERYREGISTRY_DRIVERSTOREPATH** and **D3DDDI_QUERYREGISTRY_DRIVERIMAGEPATH** are used.
However, **D3DDDI_QUERYREGISTRY_DRIVERSTOREPATH** and **D3DDDI_QUERYREGISTRY_DRIVERIMAGEPATH** will always act as-if **TranslatePath** were set to 1.

### MutableValue
Reserved. Callers of QueryAdapterInfo must set this value to 0.

### Reserved
Reserved. Callers of QueryAdapterInfo must set this value to 0.

### Value
*UINT Value*

The **Value** field exists to read all these flags in a raw syntax, instead of the named bitfield.

## See Also
- [D3DDDI_QUERYREGISTRY_INFO](ns-d3dukmdt-_d3dddi_queryregistry_info.md)

