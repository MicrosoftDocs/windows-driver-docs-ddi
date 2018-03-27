---
UID: NS:d3dhal._D3DHAL_DP2INDEXEDTRIANGLEFAN
title: "_D3DHAL_DP2INDEXEDTRIANGLEFAN"
author: windows-driver-content
description: D3DHAL_DP2INDEXEDTRIANGLEFAN is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDTRIANGLEFAN, and is used to render a sequence of connected triangles using vertex indices. All of the triangles share a common vertex.
old-location: display\d3dhal_dp2indexedtrianglefan.htm
old-project: display
ms.assetid: cdc3dd16-6bf2-495c-8df1-aa9c670d1e7a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2INDEXEDTRIANGLEFAN, D3DHAL_DP2INDEXEDTRIANGLEFAN, D3DHAL_DP2INDEXEDTRIANGLEFAN structure [Display Devices], LPD3DHAL_DP2INDEXEDTRIANGLEFAN, LPD3DHAL_DP2INDEXEDTRIANGLEFAN structure pointer [Display Devices], _D3DHAL_DP2INDEXEDTRIANGLEFAN, d3dhal/D3DHAL_DP2INDEXEDTRIANGLEFAN, d3dhal/LPD3DHAL_DP2INDEXEDTRIANGLEFAN, d3dstrct_72b499fd-e571-4dbb-a9b8-c2debf754b41.xml, display.d3dhal_dp2indexedtrianglefan"
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
-	D3DHAL_DP2INDEXEDTRIANGLEFAN
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2INDEXEDTRIANGLEFAN, *LPD3DHAL_DP2INDEXEDTRIANGLEFAN
---

# _D3DHAL_DP2INDEXEDTRIANGLEFAN structure


## -description


D3DHAL_DP2INDEXEDTRIANGLEFAN is parsed from the command buffer by the <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_INDEXEDTRIANGLEFAN, and is used to render a sequence of connected triangles using vertex indices. All of the triangles share a common vertex.


## -struct-fields




### -field wV

Specifies the indexes into the vertex buffer from which the driver obtains coordinate data for the vertices making up the triangle fan. 

Although this member has only enough space to contain three indexes, this array of indexes should be treated as a variable-sized array with (<b>wPrimitiveCount</b> + 2) elements. (<b>wPrimitiveCount</b> is a member of the D3DHAL_DP2COMMAND structure.)


## -remarks




<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> should process (<b>wPrimitiveCount</b>+2) indexes from the command buffer, in effect, processing <b>wPrimitiveCount</b> D3DHAL_DP2INDEXEDTRIANGLEFAN structures. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The driver should process a total of (<b>wPrimitiveCount</b> + 2) vertices from the vertex buffer, three vertices per triangle. The sequence of triangles rendered is: (<b>wV[</b>1<b>]</b>, <b>wV[</b>2<b>]</b>, <b>wV[</b>0<b>]</b>), (<b>wV[</b>2<b>]</b>, <b>wV[</b>3<b>]</b>, <b>wV[</b>0<b>]</b>), (<b>wV[</b>3<b>]</b>, <b>wV[</b>4<b>]</b>, <b>wV[</b>0<b>]</b>), ..., (<b>wV[wPrimitiveCount]</b>, <b>wV[wPrimitiveCount]</b>+1<b>]</b>, <b>wV[</b>0<b>]</b>). Notice that all of the triangles have the vertex specified in <b>wV[</b>0<b>]</b>in common.

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff545832">D3DHAL_DP2STARTVERTEX</a> structure immediately follows the command in the command buffer. The vertex buffer indexes are relative to the vertex buffer offset specified by the <b>dwVertexOffset</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545957">D3DHAL_DRAWPRIMITIVES2DATA</a> structure plus the base offset obtained from the <b>wVStart</b> member of the D3DHAL_DP2STARTVERTEX structure.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_INDEXEDTRIANGLEFAN command, a D3DHAL_DP2STARTVERTEX offset, and a logical list of D3DHAL_DP2INDEXEDTRIANGLEFAN structures. The driver should process five vertices from the vertex buffer, rendering a fan with three triangles defined by (v[4], v[5], v[7]), (v[5], v[6], v[7]), (v[6], v[9], v[7]).

<img alt="Figure showing a buffer with a D3DDP2OP_INDEXEDTRIANGLEFAN command, a D3DHAL_DP2STARTVERTEX offset, and a list of D3DHAL_DP2INDEXEDTRIANGLEFAN structures" src="images/dp2tfani.png"/>



## -see-also




D3DDP2OP_INDEXEDTRIANGLEFAN



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545454">D3DHAL_DP2COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545832">D3DHAL_DP2STARTVERTEX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545957">D3DHAL_DRAWPRIMITIVES2DATA</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2INDEXEDTRIANGLEFAN structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

