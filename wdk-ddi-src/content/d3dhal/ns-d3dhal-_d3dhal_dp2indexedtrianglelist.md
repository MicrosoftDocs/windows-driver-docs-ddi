---
UID: NS:d3dhal._D3DHAL_DP2INDEXEDTRIANGLELIST
title: "_D3DHAL_DP2INDEXEDTRIANGLELIST"
author: windows-driver-content
description: One or more D3DHAL_DP2INDEXEDTRIANGLELIST structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDTRIANGLELIST, and are used to render a sequence of unconnected triangles using vertex indices.
old-location: display\d3dhal_dp2indexedtrianglelist.htm
old-project: display
ms.assetid: 138d226a-85ca-41d0-a0dd-2772194874e8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2INDEXEDTRIANGLELIST, D3DHAL_DP2INDEXEDTRIANGLELIST, D3DHAL_DP2INDEXEDTRIANGLELIST structure [Display Devices], LPD3DHAL_DP2INDEXEDTRIANGLELIST, LPD3DHAL_DP2INDEXEDTRIANGLELIST structure pointer [Display Devices], _D3DHAL_DP2INDEXEDTRIANGLELIST, d3dhal/D3DHAL_DP2INDEXEDTRIANGLELIST, d3dhal/LPD3DHAL_DP2INDEXEDTRIANGLELIST, d3dstrct_ee454273-b67d-4fe5-8e81-0de4ad80ce9c.xml, display.d3dhal_dp2indexedtrianglelist"
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
-	D3DHAL_DP2INDEXEDTRIANGLELIST
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2INDEXEDTRIANGLELIST, *LPD3DHAL_DP2INDEXEDTRIANGLELIST
---

# _D3DHAL_DP2INDEXEDTRIANGLELIST structure


## -description


One or more D3DHAL_DP2INDEXEDTRIANGLELIST structures are parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_INDEXEDTRIANGLELIST, and are used to render a sequence of unconnected triangles using vertex indices.


## -syntax


````
typedef struct _D3DHAL_DP2INDEXEDTRIANGLELIST {
  WORD wV1;
  WORD wV2;
  WORD wV3;
  WORD wFlags;
} D3DHAL_DP2INDEXEDTRIANGLELIST, *LPD3DHAL_DP2INDEXEDTRIANGLELIST;
````


## -struct-fields




### -field wV1

Specifies the index into the vertex buffer location containing coordinate data for the first vertex of the triangle.


### -field wV2

Specifies the index to the vertex buffer location containing coordinate data for the second vertex of the triangle.


### -field wV3

Specifies the index to the vertex buffer location containing coordinate data for the third vertex of the triangle.


### -field wFlags

Specifies the flags that describe how the driver should render the triangle. This member can be a bitwise OR of the following values: 

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DTRIFLAG_EDGEENABLE1

</td>
<td>
The driver should render the triangle edge between <b>wV1</b> and <b>wV2</b> when the fill mode is D3DFILL_WIREFRAME.

</td>
</tr>
<tr>
<td>
D3DTRIFLAG_EDGEENABLE2

</td>
<td>
The driver should render the triangle edge between <b>wV2</b> and <b>wV3</b> when the fill mode is D3DFILL_WIREFRAME.

</td>
</tr>
<tr>
<td>
D3DTRIFLAG_EDGEENABLE3

</td>
<td>
The driver should render the triangle edge between <b>wV3</b> and <b>wV1</b> when the fill mode is D3DFILL_WIREFRAME.

</td>
</tr>
<tr>
<td>
D3DTRIFLAG_EDGEENABLETRIANGLE

</td>
<td>
The driver should render all triangle edges when the fill mode is D3DFILL_WIREFRAME.

</td>
</tr>
</table>
 


## -remarks




<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should process <b>wPrimitiveCount</b> * 3 indexes from the command buffer, processing <b>wPrimitiveCount</b> D3DHAL_DP2INDEXEDTRIANGLELIST structures. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The driver should process a total of <b>wPrimitiveCount</b>*3 vertices from the vertex buffer, three vertices per triangle, for the current command. The sequence of triangles rendered is (<b>wV1</b>₀, <b>wV2</b>₀, <b>wV3</b>₀), (<b>wV1</b>₁, <b>wV2</b>₁, <b>wV3</b>₁), ..., (<b>wV1</b>ₙ, <b>wV2</b>ₙ, <b>wV3</b>ₙ), where n equals (<b>wPrimitiveCount</b>- 1). The driver should calculate the vertex locations based on the current command as follows:

<ul>
<li>
When the command is D3DDP2OP_INDEXEDTRIANGLELIST, the indexes into the vertex buffer are relative to the vertex buffer offset specified by the <b>dwVertexOffset</b> member of the <a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a> structure.

</li>
<li>
When the command is D3DDP2OP_INDEXEDTRIANGLELIST2, there is a <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2startvertex.md">D3DHAL_DP2STARTVERTEX</a> structure that immediately follows the command in the command buffer. The indexes into the vertex buffer are relative to the vertex buffer offset specified by <b>dwVertexOffset</b> plus the base offset obtained from the <b>wVStart</b> member of the D3DHAL_DP2STARTVERTEX structure.

</li>
</ul>
The following figure shows a portion of a sample command buffer containing a D3DDP2OP_INDEXEDTRIANGLELIST command and two D3DHAL_DP2INDEXEDTRIANGLELIST structures. The driver should draw two triangles âˆ’ with all edges enabled âˆ’ using the following six vertices from the vertex buffer: (v[3], v[4], v[5]), (v[0], v[1], v[2]).

<img alt="Figure showing a command buffer with a D3DDP2OP_INDEXEDTRIANGLELIST command and two D3DHAL_DP2INDEXEDTRIANGLELIST structures" src="images/dp2tlsi.png"/>
Similarly, the following figure shows a portion of a sample command buffer containing a D3DDP2OP_INDEXEDTRIANGLELIST2 command, a D3DHAL_DP2STARTVERTEX offset, and two D3DHAL_DP2INDEXEDTRIANGLELIST structures. The driver should process six vertices from the vertex buffer, rendering two triangles defined by (v[5], v[6], v[7]), (v[2], v[3], v[4]).

<img alt="Figure showing a buffer with a D3DDP2OP_INDEXEDTRIANGLELIST2 command, a D3DHAL_DP2STARTVERTEX offset, and two D3DHAL_DP2INDEXEDTRIANGLELIST structures" src="images/dp2tls2i.png"/>



## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2startvertex.md">D3DHAL_DP2STARTVERTEX</a>



D3DDP2OP_INDEXEDTRIANGLELIST



<a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a>



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 


