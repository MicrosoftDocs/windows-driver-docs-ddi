---
UID: NS:d3dkmthk._D3DKMT_CREATEHWCONTEXT
title: _D3DKMT_CREATEHWCONTEXT (d3dkmthk.h)
description: A structure holding information to create a hardware context.
old-location: display\d3dkmt_createhwcontext.htm
ms.assetid: 9B6EA552-B576-45F3-A0BD-7EB721638D7F
ms.date: 05/10/2018
keywords: ["D3DKMT_CREATEHWCONTEXT structure"]
ms.keywords: D3DKMT_CREATEHWCONTEXT, D3DKMT_CREATEHWCONTEXT structure [Display Devices], _D3DKMT_CREATEHWCONTEXT, d3dkmthk/D3DKMT_CREATEHWCONTEXT, display.d3dkmt_createhwcontext
req.header: d3dkmthk.h
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
tech.root: display
req.typenames: D3DKMT_CREATEHWCONTEXT
f1_keywords:
 - _D3DKMT_CREATEHWCONTEXT
 - d3dkmthk/_D3DKMT_CREATEHWCONTEXT
 - D3DKMT_CREATEHWCONTEXT
 - d3dkmthk/D3DKMT_CREATEHWCONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_CREATEHWCONTEXT
---

# _D3DKMT_CREATEHWCONTEXT structure


## -description

A structure holding information to create a hardware context.

## -struct-fields

### -field hDevice

Handle to the device owning this context.

### -field NodeOrdinal

Identifier for the node targeted by this context.

### -field EngineAffinity

Engine affinity within the specified node.

### -field Flags

Context creation flags.

### -field PrivateDriverDataSize

Size of private driver data.

### -field pPrivateDriverData

Private driver data.

### -field hHwContext

Handle of the created context.

