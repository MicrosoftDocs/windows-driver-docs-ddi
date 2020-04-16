---
UID: NS:d3dhal._D3DHAL_DP2TRIANGLEFAN
title: _D3DHAL_DP2TRIANGLEFAN (d3dhal.h)
description: One D3DHAL_DP2TRIANGLEFAN structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TRIANGLEFAN, and is used to render a triangle fan.
old-location: display\d3dhal_dp2trianglefan.htm
tech.root: display
ms.assetid: 563fe6c9-868e-4b84-b14b-baee8ab00a2d
ms.date: 05/10/2018
keywords: ["_D3DHAL_DP2TRIANGLEFAN structure"]
ms.keywords: "*LPD3DHAL_DP2TRIANGLEFAN, D3DHAL_DP2TRIANGLEFAN, D3DHAL_DP2TRIANGLEFAN structure [Display Devices], LPD3DHAL_DP2TRIANGLEFAN, LPD3DHAL_DP2TRIANGLEFAN structure pointer [Display Devices], _D3DHAL_DP2TRIANGLEFAN, d3dhal/D3DHAL_DP2TRIANGLEFAN, d3dhal/LPD3DHAL_DP2TRIANGLEFAN, d3dstrct_6726a70e-3ff1-4a9f-ac1e-46acf9be04e9.xml, display.d3dhal_dp2trianglefan"
f1_keywords:
 - "d3dhal/D3DHAL_DP2TRIANGLEFAN"
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
- D3DHAL_DP2TRIANGLEFAN
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2TRIANGLEFAN, *LPD3DHAL_DP2TRIANGLEFAN
---

# _D3DHAL_DP2TRIANGLEFAN structure


## -description


One D3DHAL_DP2TRIANGLEFAN structure is parsed from the command buffer by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_TRIANGLEFAN, and is used to render a triangle fan.


## -struct-fields




### -field wVStart

Specifies the index into the vertex buffer containing coordinate data for the initial vertex of the triangle fan.


## -remarks



One D3DHAL_DP2TRIANGLEFAN structure follows the D3DHAL_DP2COMMAND structure in the command buffer.


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> should process a total of <b>wPrimitiveCount</b> + 2 vertices from the vertex buffer, three vertices per triangle, rendering <b>wPrimitiveCount</b> triangles. Starting from the vertex buffer offset, the sequence of triangles rendered is (<b>wVStart </b> + 1, <b>wVStart </b> + 2, <b>wVStart </b>), (<b>wVStart </b> + 2, <b>wVStart </b> + 3, <b>wVStart </b>),..., (<b>wVStart </b> + <b>wPrimitiveCount</b>, <b>wVStart </b>+<b>wPrimitiveCount</b> + 1, <b>wVStart </b>). The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_TRIANGLEFAN command and a D3DHAL_DP2TRIANGLEFAN structure. The driver should process six vertices from the vertex buffer, rendering a fan with four triangles defined by (v[3], v[4], v[2]), (v[4], v[5], v[2]), (v[5], v[6], v[2]), (v[6], v[7], v[2]).

<img alt="Figure showing a command buffer with a D3DDP2OP_TRIANGLEFAN command and a D3DHAL_DP2TRIANGLEFAN structure" src="images/dp2tfan.png"/>



## -see-also




D3DDP2OP_TRIANGLEFAN



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

