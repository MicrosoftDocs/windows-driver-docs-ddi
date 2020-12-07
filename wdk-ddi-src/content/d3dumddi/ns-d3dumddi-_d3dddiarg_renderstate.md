---
UID: NS:d3dumddi._D3DDDIARG_RENDERSTATE
title: _D3DDDIARG_RENDERSTATE (d3dumddi.h)
description: The D3DDDIARG_RENDERSTATE structure describes how to update a specific render state.
old-location: display\d3dddiarg_renderstate.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_RENDERSTATE structure"]
ms.keywords: D3DDDIARG_RENDERSTATE, D3DDDIARG_RENDERSTATE structure [Display Devices], UMDisplayDriver_param_Structs_4d558ee2-a265-4973-90d4-917170d01ef3.xml, _D3DDDIARG_RENDERSTATE, d3dumddi/D3DDDIARG_RENDERSTATE, display.d3dddiarg_renderstate
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: D3DDDIARG_RENDERSTATE
f1_keywords:
 - _D3DDDIARG_RENDERSTATE
 - d3dumddi/_D3DDDIARG_RENDERSTATE
 - D3DDDIARG_RENDERSTATE
 - d3dumddi/D3DDDIARG_RENDERSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_RENDERSTATE
---

# _D3DDDIARG_RENDERSTATE structure


## -description

The D3DDDIARG_RENDERSTATE structure describes how to update a specific render state.

## -struct-fields

### -field State

[in] A D3DDDIRENDERSTATETYPE-typed value that indicates the render state to be updated. For a definition of each value, see the corresponding value of the <a href="/windows-hardware/drivers/ddi/d3d9types/ne-d3d9types-_d3drenderstatetype">D3DRENDERSTATETYPE</a> enumeration type in the DirectX documentation.

### -field Value

[in] The value to which the driver should update the render state that is identified by the <b>State</b> member. For more information about values that can be updated for each render state, see the definition of the corresponding render state in the <a href="/windows-hardware/drivers/ddi/d3d9types/ne-d3d9types-_d3drenderstatetype">D3DRENDERSTATETYPE</a> enumeration type in the DirectX documentation.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setrenderstate">SetRenderState</a>
