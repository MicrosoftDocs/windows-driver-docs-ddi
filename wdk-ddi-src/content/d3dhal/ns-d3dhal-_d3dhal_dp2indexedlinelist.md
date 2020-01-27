---
UID: NS:d3dhal._D3DHAL_DP2INDEXEDLINELIST
title: _D3DHAL_DP2INDEXEDLINELIST (d3dhal.h)
description: D3DHAL_DP2INDEXEDLINELIST is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDLINELIST, and is used to render the lines using vertex indices.
old-location: display\d3dhal_dp2indexedlinelist.htm
tech.root: display
ms.assetid: 6205df9f-a6b1-4dd1-97a8-5d0d57a7ddd1
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2INDEXEDLINELIST, D3DHAL_DP2INDEXEDLINELIST, D3DHAL_DP2INDEXEDLINELIST structure [Display Devices], LPD3DHAL_DP2INDEXEDLINELIST, LPD3DHAL_DP2INDEXEDLINELIST structure pointer [Display Devices], _D3DHAL_DP2INDEXEDLINELIST, d3dhal/D3DHAL_DP2INDEXEDLINELIST, d3dhal/LPD3DHAL_DP2INDEXEDLINELIST, d3dstrct_895bb4b6-3e98-4275-a61d-38d89ec23a6f.xml, display.d3dhal_dp2indexedlinelist"
f1_keywords:
 - "d3dhal/D3DHAL_DP2INDEXEDLINELIST"
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
- D3DHAL_DP2INDEXEDLINELIST
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2INDEXEDLINELIST, *LPD3DHAL_DP2INDEXEDLINELIST
---

# _D3DHAL_DP2INDEXEDLINELIST structure


## -description


D3DHAL_DP2INDEXEDLINELIST is parsed from the command buffer by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_INDEXEDLINELIST, and is used to render the lines using vertex indices.


## -struct-fields




### -field wV1

Specifies the index into the vertex buffer, identifying the first endpoint of the line.


### -field wV2

Specifies the index into the vertex buffer, identifying the second endpoint of the line.


## -remarks




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> should process (<b>wPrimitiveCount</b> * 2) indexes from the command buffer, in effect processing <b>wPrimitiveCount</b> D3DHAL_DP2INDEXEDLINELIST structures. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The driver should process a total of (<b>wPrimitiveCount</b> * 2) vertices from the vertex buffer, two vertices per line. The sequence of lines rendered is (<b>wV1</b>₀, <b>wV2</b>₀), (<b>wV1</b>₁, <b>wV2</b>₁), ..., (<b>wV1</b>ₙ,<b>wV2</b>ₙ), where n equals (<b>wPrimitiveCount</b>- 1). The driver should interpret the vertex buffer indexes based on the current command as follows:

<ul>
<li>
When the command is D3DDP2OP_INDEXEDLINELIST, the vertex buffer indexes are relative to the vertex buffer offset specified by the <b>dwVertexOffset</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_drawprimitives2data">D3DHAL_DRAWPRIMITIVES2DATA</a> structure.

</li>
<li>
When the command is D3DDP2OP_INDEXEDLINELIST2, a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2startvertex">D3DHAL_DP2STARTVERTEX</a> structure immediately follows it and precedes the D3DHAL_DP2INDEXEDLINELIST structure(s) in the command buffer. The vertex buffer indexes are relative to the vertex buffer offset specified by <b>dwVertexOffset</b> plus the base offset obtained from the <b>wVStart</b> member of the D3DHAL_DP2STARTVERTEX structure.

</li>
</ul>
The following figure shows a portion of a sample command buffer containing a D3DDP2OP_INDEXEDLINELIST command and two D3DHAL_DP2INDEXEDLINELIST structures. The driver should draw two lines using the following four vertices from the vertex buffer: (v[0], v[4]), (v[5], v[6]).

<img alt="Figure showing a command buffer with a D3DDP2OP_INDEXEDLINELIST command and two D3DHAL_DP2INDEXEDLINELIST structures" src="images/dp2llsti.png"/>
Similarly, the following figure shows a portion of a sample command buffer containing a D3DDP2OP_INDEXEDLINELIST2 command, a D3DHAL_DP2STARTVERTEX offset, and two D3DHAL_DP2INDEXEDLINELIST structures. The driver should process four vertices from the vertex buffer, rendering two lines defined by (v[3], v[7]), (v[8], v[9]).

<img alt="Figure showing a command buffer with a D3DDP2OP_INDEXEDLINELIST2 command, a D3DHAL_DP2STARTVERTEX offset, and two D3DHAL_DP2INDEXEDLINELIST structures" src="images/dp2ll2i.png"/>



## -see-also




D3DDP2OP_INDEXEDLINELIST



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2startvertex">D3DHAL_DP2STARTVERTEX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_drawprimitives2data">D3DHAL_DRAWPRIMITIVES2DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

