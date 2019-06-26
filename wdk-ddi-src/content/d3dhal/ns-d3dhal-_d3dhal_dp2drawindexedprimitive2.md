---
UID: NS:d3dhal._D3DHAL_DP2DRAWINDEXEDPRIMITIVE2
title: _D3DHAL_DP2DRAWINDEXEDPRIMITIVE2 (d3dhal.h)
description: DirectX 8.0 and later versions only.
old-location: display\d3dhal_dp2drawindexedprimitive2.htm
tech.root: display
ms.assetid: 0376a2ce-2f1f-4515-b80a-2ecf0941d7d3
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE2, D3DHAL_DP2DRAWINDEXEDPRIMITIVE2, D3DHAL_DP2DRAWINDEXEDPRIMITIVE2 structure [Display Devices], LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE2, LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE2 structure pointer [Display Devices], _D3DHAL_DP2DRAWINDEXEDPRIMITIVE2, d3dhal/D3DHAL_DP2DRAWINDEXEDPRIMITIVE2, d3dhal/LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE2, d3dstrct_43a90135-93f4-4304-9967-b4d7b6616198.xml, display.d3dhal_dp2drawindexedprimitive2"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- D3DHAL_DP2DRAWINDEXEDPRIMITIVE2
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2DRAWINDEXEDPRIMITIVE2
---

# _D3DHAL_DP2DRAWINDEXEDPRIMITIVE2 structure


## -description



   DirectX 8.0 and later versions only.
   

D3DHAL_DRAWINDEXEDPRIMITIVE2 is parsed from the command buffer by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_DRAWINDEXEDPRIMITIVE2, and is used to render a primitive using vertex indices.


## -struct-fields




### -field primType

Specifies the type of primitive to draw (one of D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP or D3DPT_TRIANGLEFAN).


### -field BaseVertexOffset

Specifies the offset that should be added to each vertex in vertex stream 0 by the various primitives to determine the actual vertex in vertex stream 0. This offset could be negative, but when an index is added to the offset the result is positive.


### -field MinIndex

Specifies the minimum index of a range of vertices that are potentially accessed by the primitives to be drawn and, therefore, which vertices should be processed.


### -field NumVertices

Specifies the number of vertices in a range that are potentially accessed by the primitives to be drawn and, therefore, which vertices should be processed.


### -field StartIndexOffset

Specifies the offset of the first index in the index buffer from which indices are read to draw the primitives.


### -field PrimitiveCount

Specifies the number of triangles, lines or points to draw for the given primitive.


## -remarks



The vertex data has been transformed by the runtime.

As with vertices, the actual indices to use are not passed with the token data, but rather should be read from the currently selected index buffer. See <a href="https://docs.microsoft.com/windows-hardware/drivers/display/index-buffers">Index Buffers</a> for more details.




## -see-also




D3DDP2OP_DRAWINDEXEDPRIMITIVE2



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3dhal_dp2drawindexedprimitive2">D3DHAL_DP2DRAWINDEXEDPRIMITIVE2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

