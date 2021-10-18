---
UID: NS:d3dkmddi._DXGK_INVALIDATEHWCONTEXTFLAGS
title: DXGK_INVALIDATEHWCONTEXTFLAGS (d3dkmddi.h)
description: Learn more about DXGK_INVALIDATEHWCONTEXTFLAGS
ms.date: 10/13/2021
keywords: ["DXGK_INVALIDATEHWCONTEXTFLAGS structure"]
ms.keywords: _DXGK_INVALIDATEHWCONTEXTFLAGS, DXGK_INVALIDATEHWCONTEXTFLAGS,
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_INVALIDATEHWCONTEXTFLAGS
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _DXGK_INVALIDATEHWCONTEXTFLAGS
 - d3dkmddi/_DXGK_INVALIDATEHWCONTEXTFLAGS
 - DXGK_INVALIDATEHWCONTEXTFLAGS
 - d3dkmddi/DXGK_INVALIDATEHWCONTEXTFLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_INVALIDATEHWCONTEXTFLAGS
 - DXGK_INVALIDATEHWCONTEXTFLAGS
dev_langs:
 - c++
---

# DXGK_INVALIDATEHWCONTEXTFLAGS structure

## -description

**DXGK_INVALIDATEHWCONTEXTFLAGS** contains flag values associated with a context being invalidated.

## -struct-fields

### -field CollateralDamage

Identifies the scope of the collateral damage to the context being invalidated. **CollateralDamage** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| 0     | The context being invalidated was the primary cause of the engine hang. |
| 1     | The context being invalidated was not the primary cause of the engine hang, but still needs to be reset because it was affected by the hang. |

### -field Reserved

Reserved for internal use.

### -field Value

The value of the context flag.

## -see-also

[**DXGKARGCB_INVALIDATEHWCONTEXT**](ns-d3dkmddi-_dxgkargcb_invalidatehwcontext.md)

[**DXGKCB_INVALIDATEHWCONTEXT**](nc-d3dkmddi-dxgkcb_invalidatehwcontext.md)
