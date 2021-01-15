---
UID: NS:d3dumddi._D3DDDICB_CREATEHWCONTEXT
title: _D3DDDICB_CREATEHWCONTEXT (d3dumddi.h)
description: A structure that gives information for creating a hardware context.
old-location: display\d3dddicb_createhwcontext.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDICB_CREATEHWCONTEXT structure"]
ms.keywords: D3DDDICB_CREATEHWCONTEXT, D3DDDICB_CREATEHWCONTEXT structure [Display Devices], _D3DDDICB_CREATEHWCONTEXT, d3dumddi/D3DDDICB_CREATEHWCONTEXT, display.d3dddicb_createhwcontext
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: D3DDDICB_CREATEHWCONTEXT
f1_keywords:
 - _D3DDDICB_CREATEHWCONTEXT
 - d3dumddi/_D3DDDICB_CREATEHWCONTEXT
 - D3DDDICB_CREATEHWCONTEXT
 - d3dumddi/D3DDDICB_CREATEHWCONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDICB_CREATEHWCONTEXT
 - D3DDDICB_CREATEHWCONTEXT
---

# _D3DDDICB_CREATEHWCONTEXT structure


## -description

A structure that gives information for creating a hardware context.

## -struct-fields

### -field NodeOrdinal

Specifies the node ordinal this context is targeted to.

### -field EngineAffinity

Specifies the engine affinity within the node.

### -field Flags

Hardware context creation flags.

### -field PrivateDriverDataSize

Size of private driver data.

### -field pPrivateDriverData

Pointer to private driver data.

### -field hHwContext

Handle to the created context.

