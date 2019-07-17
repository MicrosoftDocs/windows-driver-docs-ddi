---
UID: NS:d3dhal._D3DHAL_DP2DRAWPRIMITIVE
title: _D3DHAL_DP2DRAWPRIMITIVE (d3dhal.h)
description: DirectX 8.0 and later versions only. D3DHAL_DRAWPRIMITIVE is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_DRAWPRIMITIVE, and is used to render a primitive.
old-location: display\d3dhal_dp2drawprimitive.htm
tech.root: display
ms.assetid: 1dd56465-e9e8-4a79-8533-a1777cf4d8a2
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2DRAWPRIMITIVE, D3DHAL_DP2DRAWPRIMITIVE, D3DHAL_DP2DRAWPRIMITIVE structure [Display Devices], LPD3DHAL_DP2DRAWPRIMITIVE, LPD3DHAL_DP2DRAWPRIMITIVE structure pointer [Display Devices], _D3DHAL_DP2DRAWPRIMITIVE, d3dhal/D3DHAL_DP2DRAWPRIMITIVE, d3dhal/LPD3DHAL_DP2DRAWPRIMITIVE, d3dstrct_2736a73d-52f8-4647-86c3-2c362dc3f669.xml, display.d3dhal_dp2drawprimitive"
ms.topic: struct
f1_keywords:
 - "d3dhal/D3DHAL_DP2DRAWPRIMITIVE"
req.header: d3dhal.h
req.include-header: D3dhal.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- D3DHAL_DP2DRAWPRIMITIVE
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2DRAWPRIMITIVE
---

# _D3DHAL_DP2DRAWPRIMITIVE structure


## -description



   DirectX 8.0 and later versions only.
   

D3DHAL_DRAWPRIMITIVE is parsed from the command buffer by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_DRAWPRIMITIVE, and is used to render a primitive.


## -struct-fields




### -field primType

Specifies the type of primitive to draw (one of D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP or D3DPT_TRIANGLEFAN).


### -field VStart

Specifies the index (into each active vertex stream) of the vertex elements with which to start drawing. Actual vertex data should be read from the current vertex streams (those referenced by the current vertex shader) rather than from the vertex data pointer in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3dhal_drawprimitives2data">D3DHAL_DRAWPRIMITIVES2DATA</a>.


### -field PrimitiveCount

Specifies the number of triangles, lines or points to draw for the given primitive.


## -remarks



The vertex data can be untransformed (if the hardware supports hardware vertex processing) or transformed if the application supplied data in that form to the runtime.




## -see-also




D3DDP2OP_DRAWPRIMITIVE



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3dhal_drawprimitives2data">D3DHAL_DRAWPRIMITIVES2DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

