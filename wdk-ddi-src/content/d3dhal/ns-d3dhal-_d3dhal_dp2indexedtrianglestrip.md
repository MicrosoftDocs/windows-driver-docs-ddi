---
UID: NS:d3dhal._D3DHAL_DP2INDEXEDTRIANGLESTRIP
title: _D3DHAL_DP2INDEXEDTRIANGLESTRIP (d3dhal.h)
description: One or more D3DHAL_DP2INDEXEDTRIANGLESTRIP structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDTRIANGLESTRIP, and are used to render strips of connected triangles using vertex indices.
old-location: display\d3dhal_dp2indexedtrianglestrip.htm
tech.root: display
ms.assetid: 542f89f1-f562-4293-9ca1-96e7a0512772
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2INDEXEDTRIANGLESTRIP, D3DHAL_DP2INDEXEDTRIANGLESTRIP, D3DHAL_DP2INDEXEDTRIANGLESTRIP structure [Display Devices], LPD3DHAL_DP2INDEXEDTRIANGLESTRIP, LPD3DHAL_DP2INDEXEDTRIANGLESTRIP structure pointer [Display Devices], _D3DHAL_DP2INDEXEDTRIANGLESTRIP, d3dhal/D3DHAL_DP2INDEXEDTRIANGLESTRIP, d3dhal/LPD3DHAL_DP2INDEXEDTRIANGLESTRIP, d3dstrct_72ed98e7-63f2-42ec-bcc4-4c4e6184cae5.xml, display.d3dhal_dp2indexedtrianglestrip"
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
-	D3DHAL_DP2INDEXEDTRIANGLESTRIP
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2INDEXEDTRIANGLESTRIP, *LPD3DHAL_DP2INDEXEDTRIANGLESTRIP
---

# _D3DHAL_DP2INDEXEDTRIANGLESTRIP structure


## -description


One or more D3DHAL_DP2INDEXEDTRIANGLESTRIP structures are parsed from the command buffer by the <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_INDEXEDTRIANGLESTRIP, and are used to render strips of connected triangles using vertex indices.


## -struct-fields




### -field wV

Specifies the index into the vertex buffer containing coordinate data for the first vertex of the triangle strip.

Although this member has only enough space to contain three indexes, this array of indexes should be treated as a variable-sized array with (<b>wPrimitiveCount</b> + 2) elements. (<b>wPrimitiveCount</b> is a member of the D3DHAL_DP2COMMAND structure.)


## -remarks




<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> should process (<b>wPrimitiveCount</b>+2) indexes from the command buffer, in effect, processing <b>wPrimitiveCount</b> D3DHAL_DP2INDEXEDTRIANGLESTRIP structures.

The triangle edges in a triangle strip are rendered in this order: (<b>wV[</b>0<b>]</b>, <b>wV[</b>1<b>]</b>, <b>wV[</b>2<b>]</b>), (<b>wV[</b>1<b>]</b>, <b>wV[</b>3<b>]</b>, <b>wV[</b>2<b>]</b>), (<b>wV[</b>2<b>]</b>, <b>wV[</b>3<b>]</b>, <b>wV[</b>4<b>]</b>), (<b>wV[</b>3<b>]</b>, <b>wV[</b>5<b>]</b>, <b>wV[</b>4<b>]</b>),...

For the last triangle in the triangle strip, however, the edges are rendered in different orders when <b>wPrimitiveCount</b>t is odd and when it is even.

<ul>
<li>
When <b>wPrimitiveCount</b> is an odd number, the last triangle's edges are rendered in this order: (<b>wV[wPrimitiveCount </b>- 1<b>]</b>, <b>wV[wPrimitiveCount]</b>, <b>wV[wPrimitiveCount</b>+ 1<b>]</b>).

</li>
<li>
When <b>wPrimitiveCount</b> is an even number, the last triangle's edges are rendered in this order: (<b>wV[wPrimitiveCount</b>- 1<b>]</b>, <b>wV[wPrimitiveCount</b>+1<b>]</b>, <b>wV[wPrimitiveCount</b>).

</li>
</ul>
A <a href="https://msdn.microsoft.com/library/windows/hardware/ff545832">D3DHAL_DP2STARTVERTEX</a> structure immediately follows the command in the command buffer. The vertex buffer indexes are relative to the vertex buffer offset specified by the <b>dwVertexOffset</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545957">D3DHAL_DRAWPRIMITIVES2DATA</a> structure plus the base offset obtained from the <b>wVStart</b> member of the D3DHAL_DP2STARTVERTEX structure.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_INDEXEDTRIANGLESTRIP command, a D3DHAL_DP2STARTVERTEX offset of zero, and a logical list of D3DHAL_DP2INDEXEDTRIANGLESTRIP structures. The driver should process five vertices from the vertex buffer, rendering a strip of three triangles defined by (v[1], v[3], v[6]), (v[3], v[4], v[6]), (v[6], v[4], v[5]).

<img alt="Figure showing a buffer with a D3DDP2OP_INDEXEDTRIANGLESTRIP command, a D3DHAL_DP2STARTVERTEX offset of zero, and a logical list of D3DHAL_DP2INDEXEDTRIANGLESTRIP structures" src="images/dp2tstrp.png"/>



## -see-also




D3DDP2OP_INDEXEDTRIANGLESTRIP



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545832">D3DHAL_DP2STARTVERTEX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545957">D3DHAL_DRAWPRIMITIVES2DATA</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

