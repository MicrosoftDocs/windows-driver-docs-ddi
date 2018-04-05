---
UID: NS:d3dhal._D3DHAL_DP2DRAWINDEXEDPRIMITIVE
title: "_D3DHAL_DP2DRAWINDEXEDPRIMITIVE"
author: windows-driver-content
description: DirectX 8.0 and later versions only.
old-location: display\d3dhal_dp2drawindexedprimitive.htm
old-project: display
ms.assetid: b28290c7-2c02-4422-af7b-4188d6f54b54
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE, D3DHAL_DP2DRAWINDEXEDPRIMITIVE, D3DHAL_DP2DRAWINDEXEDPRIMITIVE structure [Display Devices], LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE, LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE structure pointer [Display Devices], _D3DHAL_DP2DRAWINDEXEDPRIMITIVE, d3dhal/D3DHAL_DP2DRAWINDEXEDPRIMITIVE, d3dhal/LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE, d3dstrct_61b06507-bfbe-4733-ac52-03d27bac0a07.xml, display.d3dhal_dp2drawindexedprimitive"
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
-	D3DHAL_DP2DRAWINDEXEDPRIMITIVE
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2DRAWINDEXEDPRIMITIVE
---

# _D3DHAL_DP2DRAWINDEXEDPRIMITIVE structure


## -description



   DirectX 8.0 and later versions only.
   

D3DHAL_DRAWINDEXEDPRIMITIVE is parsed from the command buffer by the <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_DRAWINDEXEDPRIMITIVE, and is used to render a primitive using vertex indices.


## -struct-fields




### -field primType

Specifies the type of primitive to draw (one of D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP or D3DPT_TRIANGLEFAN).


### -field BaseVertexIndex

Specifies the amount that should be added to each index referenced by the various primitives to determine the actual index of the vertex elements in each vertex stream.


<dl>
<dt><b>DirectX 8.1 and earlier versions only.</b></dt>
<dt>Specified using a DWORD.</dt>
<dt><b>DirectX 9.0 and later versions only.</b></dt>
<dt>Specified using an INT.</dt>
</dl>



### -field MinIndex

Specifies the minimum index of a range of vertices that are potentially accessed by the primitives to be drawn and, therefore, which vertices should be processed.


### -field NumVertices

Specifies the number of vertices in a range that are potentially accessed by the primitives to be drawn and, therefore, which vertices should be processed.


### -field StartIndex

Specifies the first index in the index buffer from which indices are read to draw the primitives.


### -field PrimitiveCount

Specifies the number of triangles, lines or points to draw for the given primitive.


## -remarks



The vertex data can be untransformed (if the hardware supports hardware vertex processing) or transformed if the application supplied data in that form to the runtime.

As with vertices, the actual indices to use are not passed with the token data, but rather should be read from the currently selected index buffer. See <a href="https://msdn.microsoft.com/5bf7dc12-d988-4194-a81f-52c9c5356610">Index Buffers</a> for more details.




## -see-also




D3DDP2OP_DRAWINDEXEDPRIMITIVE



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545517">D3DHAL_DP2DRAWINDEXEDPRIMITIVE2</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

