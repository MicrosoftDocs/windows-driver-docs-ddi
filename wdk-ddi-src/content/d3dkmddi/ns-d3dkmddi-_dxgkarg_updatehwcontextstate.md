---
UID: NS:d3dkmddi._DXGKARG_UPDATEHWCONTEXTSTATE
title: _DXGKARG_UPDATEHWCONTEXTSTATE (d3dkmddi.h)
description: Used to update the context state.
old-location: display\dxgkarg_updatehwcontextstate.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_UPDATEHWCONTEXTSTATE structure"]
ms.keywords: DXGKARG_UPDATEHWCONTEXTSTATE, DXGKARG_UPDATEHWCONTEXTSTATE structure [Display Devices], _DXGKARG_UPDATEHWCONTEXTSTATE, d3dkmddi/DXGKARG_UPDATEHWCONTEXTSTATE, display.dxgkarg_updatehwcontextstate
req.header: d3dkmddi.h
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
req.typenames: DXGKARG_UPDATEHWCONTEXTSTATE
f1_keywords:
 - _DXGKARG_UPDATEHWCONTEXTSTATE
 - d3dkmddi/_DXGKARG_UPDATEHWCONTEXTSTATE
 - DXGKARG_UPDATEHWCONTEXTSTATE
 - d3dkmddi/DXGKARG_UPDATEHWCONTEXTSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKARG_UPDATEHWCONTEXTSTATE
---

# _DXGKARG_UPDATEHWCONTEXTSTATE structure


## -description

Used to update the context state.

## -struct-fields

### -field hHwContext

The hardware context whose priority or execution state is being changed.

### -field ContextSwitchFence

Context switch fence value associated with this state change request.

### -field Priority

Execution priority of this context relative to other running contexts on this node.

### -field Flags

Context execution state flags.

