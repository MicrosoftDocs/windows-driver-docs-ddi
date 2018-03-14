---
UID: NS:d3dhal._D3DHAL_DP2DRAWPRIMITIVE2
title: "_D3DHAL_DP2DRAWPRIMITIVE2"
author: windows-driver-content
description: DirectX 8.0 and later versions only. D3DHAL_DRAWPRIMITIVE2 is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_DRAWPRIMITIVE2, and is used to render a primitive.
old-location: display\d3dhal_dp2drawprimitive2.htm
old-project: display
ms.assetid: de73a814-2406-4976-ae12-909ed820586c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2DRAWPRIMITIVE2, D3DHAL_DP2DRAWPRIMITIVE2, D3DHAL_DP2DRAWPRIMITIVE2 structure [Display Devices], LPD3DHAL_DP2DRAWPRIMITIVE2, LPD3DHAL_DP2DRAWPRIMITIVE2 structure pointer [Display Devices], _D3DHAL_DP2DRAWPRIMITIVE2, d3dhal/D3DHAL_DP2DRAWPRIMITIVE2, d3dhal/LPD3DHAL_DP2DRAWPRIMITIVE2, d3dstrct_b61a4b46-344e-4f06-9b2b-1434bb8b6dcc.xml, display.d3dhal_dp2drawprimitive2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_DP2DRAWPRIMITIVE2
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2DRAWPRIMITIVE2
---

# _D3DHAL_DP2DRAWPRIMITIVE2 structure


## -description



   DirectX 8.0 and later versions only.
   

D3DHAL_DRAWPRIMITIVE2 is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_DRAWPRIMITIVE2, and is used to render a primitive.


## -syntax


````
typedef struct _D3DHAL_DP2DRAWPRIMITIVE2 {
  D3DPRIMITIVETYPE primType;
  DWORD            FirstVertexOffset;
  DWORD            PrimitiveCount;
} D3DHAL_DP2DRAWPRIMITIVE2, *LPD3DHAL_DP2DRAWPRIMITIVE2;
````


## -struct-fields




### -field primType

Specifies the type of primitive to draw (one of D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP or D3DPT_TRIANGLEFAN).


### -field FirstVertexOffset

Specifies the offset, in bytes, in stream zero of the vertex data. This is in contrast to D3DDP2OP_DRAWPRIMITIVE where the start of the vertex data in the vertex stream is specified by a vertex index rather than an actual byte offset.


### -field PrimitiveCount

Specifies the number of triangles, lines or points to draw for the given primitive.


## -remarks



The vertex data has been transformed by the runtime.




## -see-also

D3DDP2OP_DRAWPRIMITIVE



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2drawprimitive.md">D3DHAL_DP2DRAWPRIMITIVE</a>



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



D3DDP2OP_DRAWPRIMITIVE2



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 


