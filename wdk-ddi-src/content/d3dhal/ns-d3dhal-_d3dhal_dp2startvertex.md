---
UID: NS:d3dhal._D3DHAL_DP2STARTVERTEX
title: _D3DHAL_DP2STARTVERTEX (d3dhal.h)
description: A D3DHAL_DP2STARTVERTEX structure follows certain D3DHAL_DP2COMMAND structures in the command buffer, and indicates the offset in the vertex buffer for the first vertex to use in D3dDrawPrimitives2.
old-location: display\d3dhal_dp2startvertex.htm
tech.root: display
ms.assetid: 302ed135-9fde-4101-876f-1f70bed501b0
ms.date: 05/10/2018
keywords: ["_D3DHAL_DP2STARTVERTEX structure"]
ms.keywords: "*LPD3DHAL_DP2STARTVERTEX, D3DHAL_DP2STARTVERTEX, D3DHAL_DP2STARTVERTEX structure [Display Devices], LPD3DHAL_DP2STARTVERTEX, LPD3DHAL_DP2STARTVERTEX structure pointer [Display Devices], _D3DHAL_DP2STARTVERTEX, d3dhal/D3DHAL_DP2STARTVERTEX, d3dhal/LPD3DHAL_DP2STARTVERTEX, d3dstrct_1dafced6-8893-45ac-b5a2-8735fe3dbd6a.xml, display.d3dhal_dp2startvertex"
f1_keywords:
 - "d3dhal/D3DHAL_DP2STARTVERTEX"
 - "D3DHAL_DP2STARTVERTEX"
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
- D3DHAL_DP2STARTVERTEX
targetos: Windows
req.typenames: D3DHAL_DP2STARTVERTEX, *LPD3DHAL_DP2STARTVERTEX
---

# _D3DHAL_DP2STARTVERTEX structure


## -description


A D3DHAL_DP2STARTVERTEX structure follows certain <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structures in the command buffer, and indicates the offset in the vertex buffer for the first vertex to use in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>.


## -struct-fields




### -field wVStart

Specifies an additional offset to be added to any index used for determining the location of vertices in the vertex buffer (in the case of indexed primitives).


## -remarks



A D3DHAL_DP2STARTVERTEX structure follows a D3DHAL_DP2COMMAND structure in the command buffer when the <b>bCommand</b> member of D3DHAL_DP2COMMAND is one of the following values:

<ul>
<li>
D3DDP2OP_INDEXEDLINELIST2

</li>
<li>
D3DDP2OP_INDEXEDLINESTRIP

</li>
<li>
D3DDP2OP_INDEXEDTRIANGLELIST2

</li>
<li>
D3DDP2OP_INDEXEDTRIANGLESTRIP

</li>
<li>
D3DDP2OP_INDEXEDTRIANGLEFAN

</li>
</ul>
The first vertex of such primitives is located (<b>wVStart</b> + <b>dwVertexOffset</b>) bytes from the beginning of the vertex buffer, where <b>dwVertexOffset</b> is a member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_drawprimitives2data">D3DHAL_DRAWPRIMITIVES2DATA</a>.




## -see-also




D3DDP2OP_INDEXEDLINELIST2



D3DDP2OP_INDEXEDLINESTRIP



D3DDP2OP_INDEXEDTRIANGLEFAN



D3DDP2OP_INDEXEDTRIANGLELIST2



D3DDP2OP_INDEXEDTRIANGLESTRIP



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_drawprimitives2data">D3DHAL_DRAWPRIMITIVES2DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

