---
UID: NS:d3dhal._D3DHAL_DP2INDEXEDLINESTRIP
title: _D3DHAL_DP2INDEXEDLINESTRIP (d3dhal.h)
description: D3DHAL_DP2INDEXEDLINESTRIP is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDLINESTRIP, and is used to render a sequence of connected line segments using vertex indices.
old-location: display\d3dhal_dp2indexedlinestrip.htm
tech.root: display
ms.assetid: 92809162-c39e-4dbb-9ab1-a5b6535d5beb
ms.date: 05/10/2018
keywords: ["_D3DHAL_DP2INDEXEDLINESTRIP structure"]
ms.keywords: "*LPD3DHAL_DP2INDEXEDLINESTRIP, D3DHAL_DP2INDEXEDLINESTRIP, D3DHAL_DP2INDEXEDLINESTRIP structure [Display Devices], LPD3DHAL_DP2INDEXEDLINESTRIP, LPD3DHAL_DP2INDEXEDLINESTRIP structure pointer [Display Devices], _D3DHAL_DP2INDEXEDLINESTRIP, d3dhal/D3DHAL_DP2INDEXEDLINESTRIP, d3dhal/LPD3DHAL_DP2INDEXEDLINESTRIP, d3dstrct_ab23071d-9180-48d0-b14c-7c8005652968.xml, display.d3dhal_dp2indexedlinestrip"
f1_keywords:
 - "d3dhal/D3DHAL_DP2INDEXEDLINESTRIP"
 - "D3DHAL_DP2INDEXEDLINESTRIP"
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
- D3DHAL_DP2INDEXEDLINESTRIP
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2INDEXEDLINESTRIP, *LPD3DHAL_DP2INDEXEDLINESTRIP
---

# _D3DHAL_DP2INDEXEDLINESTRIP structure


## -description


D3DHAL_DP2INDEXEDLINESTRIP is parsed from the command buffer by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_INDEXEDLINESTRIP, and is used to render a sequence of connected line segments using vertex indices.


## -struct-fields




### -field wV

Specifies the indexes into the vertex buffer from which the driver obtains coordinate data for the vertices making up the line strip. 

Although this member has only enough space to hold two indexes, this array of indexes should be treated as a variable-sized array with (<b>wPrimitiveCount</b>+ 1) elements. (<b>wPrimitiveCount</b> is a member of the D3DHAL_DP2COMMAND structure.)


## -remarks



Indexed line strips rendered with vertex buffers are specified using D3DHAL_DP2INDEXEDLINESTRIP. The number of line segments to process is specified by the <b>wPrimitiveCount</b> member of D3DHAL_DP2COMMAND. The sequence of line segments rendered is: (<b>wV[</b>0<b>]</b>, <b>wV[</b>1<b>]</b>), (<b>wV[</b>1<b>]</b>, <b>wV[</b>2<b>]</b>), (<b>wV[</b>2<b>]</b>, <b>wV[</b>3<b>]</b>), ..., (<b>wVStart[wPrimitiveCount</b> -1<b>]</b>, <b>wVStart[wPrimitiveCount]</b>). 


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> should process (<b>wPrimitiveCount</b>+1) indexes from the command buffer, in effect processing <b>wPrimitiveCount</b> D3DHAL_DP2INDEXEDLINESTRIP structures. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2startvertex">D3DHAL_DP2STARTVERTEX</a> structure immediately follows the command in the command buffer. The vertex buffer indexes are relative to the vertex buffer offset specified by the <b>dwVertexOffset</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_drawprimitives2data">D3DHAL_DRAWPRIMITIVES2DATA</a> structure plus the base offset obtained from the <b>wVStart</b> member of the D3DHAL_DP2STARTVERTEX structure.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_INDEXEDLINESTRIP command, a D3DHAL_DP2STARTVERTEX offset, and a list of D3DHAL_DP2INDEXEDLINESTRIP structures. The driver should process four vertices from the vertex buffer, rendering three connected line segments defined by (v[8], v[4]), (v[4], v[7]), (v[7], v[6]).

<img alt="Figure showing a buffer with a D3DDP2OP_INDEXEDLINESTRIP command, a D3DHAL_DP2STARTVERTEX offset, and a list of D3DHAL_DP2INDEXEDLINESTRIP structures" src="images/dp2lstri.png"/>



## -see-also




D3DDP2OP_INDEXEDLINESTRIP



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2startvertex">D3DHAL_DP2STARTVERTEX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_drawprimitives2data">D3DHAL_DRAWPRIMITIVES2DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

