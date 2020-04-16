---
UID: NS:d3dhal._D3DHAL_DP2LINESTRIP
title: _D3DHAL_DP2LINESTRIP (d3dhal.h)
description: One D3DHAL_DP2LINESTRIP structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_LINESTRIP, and is used to render the specified connected line segments.
old-location: display\d3dhal_dp2linestrip.htm
tech.root: display
ms.assetid: 1f893474-c132-4843-985a-5ef1d0d8f32d
ms.date: 05/10/2018
keywords: ["_D3DHAL_DP2LINESTRIP structure"]
ms.keywords: "*LPD3DHAL_DP2LINESTRIP, D3DHAL_DP2LINESTRIP, D3DHAL_DP2LINESTRIP structure [Display Devices], LPD3DHAL_DP2LINESTRIP, LPD3DHAL_DP2LINESTRIP structure pointer [Display Devices], _D3DHAL_DP2LINESTRIP, d3dhal/D3DHAL_DP2LINESTRIP, d3dhal/LPD3DHAL_DP2LINESTRIP, d3dstrct_d49daf52-1228-463a-8db5-3802da2fc787.xml, display.d3dhal_dp2linestrip"
f1_keywords:
 - "d3dhal/D3DHAL_DP2LINESTRIP"
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
- D3DHAL_DP2LINESTRIP
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2LINESTRIP, *LPD3DHAL_DP2LINESTRIP
---

# _D3DHAL_DP2LINESTRIP structure


## -description


One D3DHAL_DP2LINESTRIP structure is parsed from the command buffer by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_LINESTRIP, and is used to render the specified connected line segments.


## -struct-fields




### -field wVStart

Specifies the index into the vertex buffer containing coordinate data for the initial vertex of the line strip.


## -remarks



One D3DHAL_DP2LINESTRIP structure follows the D3DHAL_DP2COMMAND structure in the command buffer.


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> should sequentially process a total of (<b>wPrimitiveCount</b> + 1) vertices from the vertex buffer. Starting from the vertex buffer offset, the sequence of lines rendered is (<b>wVStart</b>, <b>wVStart</b> + 1), (<b>wVStart</b> + 1, <b>wVStart</b> + 2), (<b>wVStart</b> + 2, <b>wVStart</b> + 3), ..., (<b>wVStart</b> + (<b>wPrimitiveCount</b> - 1), <b>wVStart</b> + <b>wPrimitiveCount</b>). The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_LINESTRIP command and one D3DHAL_DP2LINESTRIP structure. The driver should draw three connected lines using the following four vertices from the vertex buffer: (v[4], v[5]), (v[5], v[6]), (v[6], v[7]).

<img alt="Figure showing a command buffer with a D3DDP2OP_LINESTRIP command and one D3DHAL_DP2LINESTRIP structure" src="images/dp2lstr.png"/>



## -see-also




D3DDP2OP_LINESTRIP



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

