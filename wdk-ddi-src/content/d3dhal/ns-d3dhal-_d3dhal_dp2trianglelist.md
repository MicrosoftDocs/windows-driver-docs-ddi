---
UID: NS:d3dhal._D3DHAL_DP2TRIANGLELIST
title: "_D3DHAL_DP2TRIANGLELIST"
author: windows-driver-content
description: One D3DHAL_DP2TRIANGLELIST structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TRIANGLELIST, and is used to render the specified unconnected triangles.
old-location: display\d3dhal_dp2trianglelist.htm
old-project: display
ms.assetid: f9a9b407-dae5-4456-8542-4f5b06af50a5
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *LPD3DHAL_DP2TRIANGLELIST, ,, 2, 3, A, D, D3DHAL_DP2TRIANGLELIST, D3DHAL_DP2TRIANGLELIST structure [Display Devices], E, G, H, I, L, LPD3DHAL_DP2TRIANGLELIST, LPD3DHAL_DP2TRIANGLELIST structure pointer [Display Devices], N, P, R, S, T, _, _D3DHAL_DP2TRIANGLELIST, d3dhal/D3DHAL_DP2TRIANGLELIST, d3dhal/LPD3DHAL_DP2TRIANGLELIST, d3dstrct_3e5f6bc4-358d-4db1-88b3-2f7c7484abb4.xml, display.d3dhal_dp2trianglelist"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dhal.h
apiname:
-	D3DHAL_DP2TRIANGLELIST
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2TRIANGLELIST, *LPD3DHAL_DP2TRIANGLELIST
---

# _D3DHAL_DP2TRIANGLELIST structure


## -description


One D3DHAL_DP2TRIANGLELIST structure is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_TRIANGLELIST, and is used to render the specified unconnected triangles.


## -syntax


````
typedef struct _D3DHAL_DP2TRIANGLELIST {
  WORD wVStart;
} D3DHAL_DP2TRIANGLELIST, *LPD3DHAL_DP2TRIANGLELIST;
````


## -struct-fields




### -field wVStart

Specifies the offset into the vertex buffer containing coordinate data for the initial vertex of the triangle list 


## -remarks



One D3DHAL_DP2TRIANGLELIST structure follows the D3DHAL_DP2COMMAND structure in the command buffer.


<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should sequentially process a total of <b>wPrimitiveCount</b> * 3 vertices from the vertex buffer, three vertices per triangle, rendering <b>wPrimitiveCount</b> triangles. Starting from the vertex buffer offset, the sequence of triangles rendered is (<b>wVStart</b>, <b>wVStart</b> + 1, <b>wVStart</b> + 2), (<b>wVStart</b> + 3, <b>wVStart</b> + 4, <b>wVStart</b> + 5),..., (<b>wVStart</b> + (<b>wPrimitiveCount</b> - 1) * 3, <b>wVStart</b> + <b>wPrimitiveCount</b> * 3 - 2, <b>wVStart</b> + <b>wPrimitiveCount</b> * 3 - 1). The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_TRIANGLELIST command and one D3DHAL_DP2TRIANGLELIST structure. The driver should draw two triangles using the following six vertices from the vertex buffer: (v[2], v[3], v[4]), (v[5], v[6], v[7]).

<img alt="Figure showing a command buffer with a D3DDP2OP_TRIANGLELIST command and one D3DHAL_DP2TRIANGLELIST structure " src="images/dp2tlist.png"/>



## -see-also

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



D3DDP2OP_TRIANGLELIST



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2TRIANGLELIST structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

