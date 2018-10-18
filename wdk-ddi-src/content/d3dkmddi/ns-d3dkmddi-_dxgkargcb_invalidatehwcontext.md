---
UID: NS:d3dkmddi._DXGKARGCB_INVALIDATEHWCONTEXT
title: _DXGKARGCB_INVALIDATEHWCONTEXT
author: windows-driver-content
description: Invalidates hardware context.
ms.assetid: 1291e94b-ddaf-43ec-a205-7dda7d63ff01
ms.date:
ms.topic: struct
ms.keywords: _DXGKARGCB_INVALIDATEHWCONTEXT, DXGKARGCB_INVALIDATEHWCONTEXT,
req.header: d3dkmddi.h
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
req.typenames: DXGKARGCB_INVALIDATEHWCONTEXT
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	_DXGKARGCB_INVALIDATEHWCONTEXT
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGKARGCB_INVALIDATEHWCONTEXT structure

## -description

Invalidates hardware context.

## -struct-fields

### -field hAdapter

[in] Handle to the display adapter.

### -field hHwContext

[in] For contexts that were invalidated by HW engine reset operation, DXG assigned value for the context that was passed to DxgkDdiCreateContext.

### -field Flags

Flags.

