---
UID: NS:d3dhal._D3DHAL_DP2TRIANGLEFAN_IMM
title: "_D3DHAL_DP2TRIANGLEFAN_IMM"
author: windows-driver-content
description: One D3DHAL_DP2TRIANGLEFAN_IMM structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TRIANGLEFAN_IMM, and is used to render a triangle fan.
old-location: display\d3dhal_dp2trianglefan_imm.htm
old-project: display
ms.assetid: a2f6f184-1178-4578-aafa-0bd088d42634
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*LPD3DHAL_DP2TRIANGLEFAN_IMM, D3DHAL_DP2TRIANGLEFAN_IMM, D3DHAL_DP2TRIANGLEFAN_IMM structure [Display Devices], LPD3DHAL_DP2TRIANGLEFAN_IMM, LPD3DHAL_DP2TRIANGLEFAN_IMM structure pointer [Display Devices], _D3DHAL_DP2TRIANGLEFAN_IMM, d3dhal/D3DHAL_DP2TRIANGLEFAN_IMM, d3dhal/LPD3DHAL_DP2TRIANGLEFAN_IMM, d3dstrct_a3365200-9001-4f6b-bb38-2ca384a89b25.xml, display.d3dhal_dp2trianglefan_imm"
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
-	D3DHAL_DP2TRIANGLEFAN_IMM
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2TRIANGLEFAN_IMM
---

# _D3DHAL_DP2TRIANGLEFAN_IMM structure


## -description


One D3DHAL_DP2TRIANGLEFAN_IMM structure is parsed from the command buffer by the <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_TRIANGLEFAN_IMM, and is used to render a triangle fan.


## -struct-fields




### -field dwEdgeFlags

Specifies a bitmask that identifies which of the fan's outside edges should be rendered when the fill mode is D3DFILL_WIREFRAME. A set bit indicates that its corresponding edge should be rendered. For more information about this bitmask, see the Remarks section.


## -remarks



One D3DHAL_DP2TRIANGLEFAN_IMM structure immediately follows the D3DHAL_DP2COMMAND structure in the command buffer. The triangle fan's vertex data is DWORD-aligned immediately following the D3DHAL_DP2TRIANGLEFAN_IMM structure in the command buffer.


<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> should process a total of <b>wPrimitiveCount</b>+2 vertices from the command buffer, three vertices per triangle, rendering <b>wPrimitiveCount</b> triangles. The sequence of triangles rendered is (<b>V[</b>1<b>]</b>, <b>V[</b>2<b>]</b>, <b>V[</b>0<b>]</b>), (<b>V[</b>2<b>]</b>, <b>V[</b>3<b>]</b>, <b>V[</b>0<b>]</b>), (<b>V[</b>3<b>]</b>, <b>V[</b>4<b>]</b>, <b>V[</b>0<b>]</b>), ..., (<b>V[wPrimitiveCount]</b>, <b>V[wPrimitiveCount]</b> + 1<b>]</b>, <b>V[</b>0<b>]</b>). The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The driver must check the edge flag for each of the fan's outside edges when the fill mode is D3DFILL_WIREFRAME. Starting from the least significant bit of <b>dwEdgeFlags</b>, bit 0 applies to the <b>V[</b>0<b>]</b>-<b>V[</b>1<b>]</b> edge, bit 1 applies to the <b>V[</b>1<b>]</b>-<b>V[</b>2<b>]</b> edge, ..., bit <b>wPrimitiveCount</b> applies to the <b>V[wPrimitiveCount]</b>-<b>V[[wPrimitiveCount]</b>+1<b>]</b> edge, and bit (<b>wPrimitiveCount</b> + 1) applies to the <b>V[[wPrimitiveCount]</b>+1<b>]</b>-<b>V[</b>0<b>]</b> edge.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_TRIANGLEFAN_IMM command, a D3DHAL_DP2TRIANGLEFAN_IMM structure, and the vertex data. The driver should process the five vertices from the command buffer, rendering a fan with three triangles defined by (v[1], v[2], v[0]), (v[2], v[3], v[0]), (v[3], v[4], v[0]).

<img alt="Figure showing a command buffer with a D3DDP2OP_TRIANGLEFAN_IMM command, a D3DHAL_DP2TRIANGLEFAN_IMM structure, and the vertex data " src="images/dp2tfimm.png"/>



## -see-also




D3DDP2OP_TRIANGLEFAN_IMM



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

