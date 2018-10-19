---
UID: NS:d3dhal._D3DHAL_DP2LINELIST
title: "_D3DHAL_DP2LINELIST"
author: windows-driver-content
description: One D3DHAL_DP2LINELIST structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_LINELIST, and is used to render unconnected line segments.
old-location: display\d3dhal_dp2linelist.htm
tech.root: display
ms.assetid: ac8346e9-46ce-4205-a46b-c327888b952d
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2LINELIST, D3DHAL_DP2LINELIST, D3DHAL_DP2LINELIST structure [Display Devices], LPD3DHAL_DP2LINELIST, LPD3DHAL_DP2LINELIST structure pointer [Display Devices], _D3DHAL_DP2LINELIST, d3dhal/D3DHAL_DP2LINELIST, d3dhal/LPD3DHAL_DP2LINELIST, d3dstrct_e2e04b99-c6fc-4ee3-bcaf-4794814848a0.xml, display.d3dhal_dp2linelist"
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
-	D3DHAL_DP2LINELIST
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2LINELIST, *LPD3DHAL_DP2LINELIST
---

# _D3DHAL_DP2LINELIST structure


## -description


One D3DHAL_DP2LINELIST structure is parsed from the command buffer by the <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_LINELIST, and is used to render unconnected line segments.


## -struct-fields




### -field wVStart

Specifies the index into the vertex buffer containing coordinate data for the initial vertex of the line list.


## -remarks



One D3DHAL_DP2LINELIST structure follows the D3DHAL_DP2COMMAND structure in the command buffer.


<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> should sequentially process a total of <b>wPrimitiveCount</b> * 2 vertices from the vertex buffer, two vertices per line, rendering a total of <b>wPrimitiveCount</b> lines. Starting from the vertex buffer offset, the sequence of lines rendered is (<b>wVStart</b>, <b>wVStart</b> + 1), (<b>wVStart</b> + 2, <b>wVStart</b> + 3),..., (<b>wVStart</b> + (<b>wPrimitiveCount</b> -1 ) * 2, <b>wVStart</b> + (<b>wPrimitiveCount</b> * 2 - 1)). The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_LINELIST command and one D3DHAL_DP2LINELIST structure. The driver should draw three lines using the following six vertices from the vertex buffer: (v[0], v[1]), (v[2], v[3]), (v[4], v[5]).

<img alt="Figure showing a command buffer with a D3DDP2OP_LINELIST command and one D3DHAL_DP2LINELIST structure" src="images/dp2lnlst.png"/>



## -see-also




D3DDP2OP_LINELIST



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

