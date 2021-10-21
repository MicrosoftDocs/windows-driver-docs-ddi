---
UID: NS:d3dkmddi._DXGKARGCB_INVALIDATEHWCONTEXT
title: DXGKARGCB_INVALIDATEHWCONTEXT (d3dkmddi.h)
description: Invalidates hardware context.
ms.date: 10/13/2021
keywords: ["DXGKARGCB_INVALIDATEHWCONTEXT structure"]
ms.keywords: _DXGKARGCB_INVALIDATEHWCONTEXT, DXGKARGCB_INVALIDATEHWCONTEXT,
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
req.typenames: DXGKARGCB_INVALIDATEHWCONTEXT
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGKARGCB_INVALIDATEHWCONTEXT
 - d3dkmddi/_DXGKARGCB_INVALIDATEHWCONTEXT
 - DXGKARGCB_INVALIDATEHWCONTEXT
 - d3dkmddi/DXGKARGCB_INVALIDATEHWCONTEXT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_INVALIDATEHWCONTEXT
 - DXGKARGCB_INVALIDATEHWCONTEXT
product:
 - Windows
---

# DXGKARGCB_INVALIDATEHWCONTEXT structure

## -description

The **DXGKARGCB_INVALIDATEHWCONTEXT** structure contains the arguments used in the [**DXGKCB_INVALIDATEHWCONTEXT**](nc-d3dkmddi-dxgkcb_invalidatehwcontext.md) callback function, to invalidate a hardware context.

## -struct-fields

### -field hAdapter [in]

Handle to the display adapter.

### -field hHwContext [in]

For contexts that were invalidated by a hardware engine reset operation, the *Dxgkrnl*-assigned value for the context that was passed to [**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md).

### -field Flags [in]

A [**DXGK_INVALIDATEHWCONTEXTFLAGS**](ns-d3dkmddi-_dxgk_invalidatehwcontextflags.md) structure that contains flag values associated with the context being invalidated.

## -see-also

[**DXGK_INVALIDATEHWCONTEXTFLAGS**](ns-d3dkmddi-_dxgk_invalidatehwcontextflags.md)

[**DXGKCB_INVALIDATEHWCONTEXT**](nc-d3dkmddi-dxgkcb_invalidatehwcontext.md)

[**DxgkDdiCreateContext**](nc-d3dkmddi-dxgkddi_createcontext.md)
