---
UID: NS:d3dhal._D3DHAL_DP2POINTS
title: _D3DHAL_DP2POINTS (d3dhal.h)
description: One or more D3DHAL_DP2POINTS structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_POINTS, and are used to render the specified points.
old-location: display\d3dhal_dp2points.htm
tech.root: display
ms.assetid: 9987ed83-7aa1-4e07-a85b-26607000ecba
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2POINTS, D3DHAL_DP2POINTS, D3DHAL_DP2POINTS structure [Display Devices], LPD3DHAL_DP2POINTS, LPD3DHAL_DP2POINTS structure pointer [Display Devices], _D3DHAL_DP2POINTS, d3dhal/D3DHAL_DP2POINTS, d3dhal/LPD3DHAL_DP2POINTS, d3dstrct_ab7299b5-74b9-43bb-8784-6c1249e23f2f.xml, display.d3dhal_dp2points"
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
- D3DHAL_DP2POINTS
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2POINTS, *LPD3DHAL_DP2POINTS
---

# _D3DHAL_DP2POINTS structure


## -description


One or more D3DHAL_DP2POINTS structures are parsed from the command buffer by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_POINTS, and are used to render the specified points.


## -struct-fields




### -field wCount

Specifies the number of points to render.


### -field wVStart

Specifies the index into the vertex buffer containing coordinate data for the initial point.


## -remarks




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> should process <b>wPrimitiveCount</b> D3DHAL_DP2POINTS structures from the command buffer. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

For each D3DHAL_DP2POINTS structure, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> should sequentially process <b>wCount</b> vertices from the vertex buffer. Starting from the vertex buffer offset, the sequence of points rendered is <b>wVStart</b>, (<b>wVStart</b>+1), ..., (<b>wVStart</b>+(<b>wCount</b>-1)).

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_POINTS command and two D3DHAL_DP2POINTS structures. The driver should draw a total of seven points using the following vertices from the vertex buffer: v[2], v[3], v[4], v[7], v[8], v[9], v[10].

<img alt="Figure showing a command buffer with a D3DDP2OP_POINTS command and two D3DHAL_DP2POINTS structures" src="images/dp2pnts.png"/>



## -see-also




D3DDP2OP_POINTS



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

