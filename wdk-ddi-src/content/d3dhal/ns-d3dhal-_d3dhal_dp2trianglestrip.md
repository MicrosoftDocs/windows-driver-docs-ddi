---
UID: NS:d3dhal._D3DHAL_DP2TRIANGLESTRIP
title: "_D3DHAL_DP2TRIANGLESTRIP"
description: One D3DHAL_DP2TRIANGLESTRIP structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TRIANGLESTRIP, and is used to render the specified connected triangle strip.
old-location: display\d3dhal_dp2trianglestrip.htm
tech.root: display
ms.assetid: dfa4f6c3-b174-4bd5-9729-6d835bb87b6a
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2TRIANGLESTRIP, D3DHAL_DP2TRIANGLESTRIP, D3DHAL_DP2TRIANGLESTRIP structure [Display Devices], LPD3DHAL_DP2TRIANGLESTRIP, LPD3DHAL_DP2TRIANGLESTRIP structure pointer [Display Devices], _D3DHAL_DP2TRIANGLESTRIP, d3dhal/D3DHAL_DP2TRIANGLESTRIP, d3dhal/LPD3DHAL_DP2TRIANGLESTRIP, d3dstrct_01322dae-8b16-4631-ac3d-f65c5d31c5a3.xml, display.d3dhal_dp2trianglestrip"
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
-	D3DHAL_DP2TRIANGLESTRIP
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2TRIANGLESTRIP, *LPD3DHAL_DP2TRIANGLESTRIP
---

# _D3DHAL_DP2TRIANGLESTRIP structure


## -description


One D3DHAL_DP2TRIANGLESTRIP structure is parsed from the command buffer by the <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_TRIANGLESTRIP, and is used to render the specified connected triangle strip.


## -struct-fields




### -field wVStart

Specifies the index to the vertex buffer containing coordinate data for the initial vertex of the triangle strip.


## -remarks



One D3DHAL_DP2TRIANGLESTRIP structure follows the D3DHAL_DP2COMMAND structure in the command buffer.


<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> should process a total of (<b>wPrimitiveCount</b> + 2) vertices from the vertex buffer. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The triangle edges in a triangle strip are rendered in this order: (<b>wV[</b>0<b>]</b>, <b>wV[</b>1<b>]</b>, <b>wV[</b>2<b>]</b>), (<b>wV[</b>1<b>]</b>, <b>wV[</b>3<b>]</b>, <b>wV[</b>2<b>]</b>), (<b>wV[</b>2<b>]</b>, <b>wV[</b>3<b>]</b>, <b>wV[</b>4<b>]</b>), (<b>wV[</b>3<b>]</b>, <b>wV[</b>5<b>]</b>, <b>wV[</b>4<b>]</b>),...

For the last triangle in the triangle strip, however, the edges are rendered in different orders when <b>wPrimitiveCount</b>t is odd and when it is even.

<ul>
<li>
When <b>wPrimitiveCount</b> is an odd number, the last triangle's edges are rendered in this order: (<b>wV[wPrimitiveCount</b> - 1<b>]</b>, <b>wV[wPrimitiveCount]</b>, <b>wV[wPrimitiveCount </b>+ 1<b>]</b>).

</li>
<li>
When <b>wPrimitiveCount</b> is an even number, the last triangle's edges are rendered in this order: (<b>wV[wPrimitiveCount</b>- 1<b>]</b>, <b>wV[wPrimitiveCount</b> + 1<b>]</b>, <b>wV[wPrimitiveCount</b>).

</li>
</ul>
The following figure shows a portion of a sample command buffer containing a D3DDP2OP_TRIANGLESTRIP command and one D3DHAL_DP2TRIANGLESTRIP structure. The driver should process five vertices from the vertex buffer, rendering a strip of three triangles defined by (v[0], v[1], v[2]), (v[1], v[3], v[2]), (v[2], v[3], v[4]).

<img alt="Figure showing a command buffer with a D3DDP2OP_TRIANGLESTRIP command and one D3DHAL_DP2TRIANGLESTRIP structure" src="images/dp2trist.png"/>



## -see-also




D3DDP2OP_TRIANGLESTRIP



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

