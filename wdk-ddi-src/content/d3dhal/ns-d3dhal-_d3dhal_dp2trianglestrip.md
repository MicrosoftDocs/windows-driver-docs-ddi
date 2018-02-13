---
UID: NS:d3dhal._D3DHAL_DP2TRIANGLESTRIP
title: "_D3DHAL_DP2TRIANGLESTRIP"
author: windows-driver-content
description: One D3DHAL_DP2TRIANGLESTRIP structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_TRIANGLESTRIP, and is used to render the specified connected triangle strip.
old-location: display\d3dhal_dp2trianglestrip.htm
old-project: display
ms.assetid: dfa4f6c3-b174-4bd5-9729-6d835bb87b6a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dhal/D3DHAL_DP2TRIANGLESTRIP, D3DHAL_DP2TRIANGLESTRIP structure [Display Devices], D3DHAL_DP2TRIANGLESTRIP, display.d3dhal_dp2trianglestrip, *LPD3DHAL_DP2TRIANGLESTRIP, d3dstrct_01322dae-8b16-4631-ac3d-f65c5d31c5a3.xml, LPD3DHAL_DP2TRIANGLESTRIP, LPD3DHAL_DP2TRIANGLESTRIP structure pointer [Display Devices], d3dhal/LPD3DHAL_DP2TRIANGLESTRIP, _D3DHAL_DP2TRIANGLESTRIP
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
-	D3DHAL_DP2TRIANGLESTRIP
product: Windows
targetos: Windows
req.typenames: "*LPD3DHAL_DP2TRIANGLESTRIP, D3DHAL_DP2TRIANGLESTRIP"
---

# _D3DHAL_DP2TRIANGLESTRIP structure


## -description


One D3DHAL_DP2TRIANGLESTRIP structure is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_TRIANGLESTRIP, and is used to render the specified connected triangle strip.


## -syntax


````
typedef struct _D3DHAL_DP2TRIANGLESTRIP {
  WORD wVStart;
} D3DHAL_DP2TRIANGLESTRIP, *LPD3DHAL_DP2TRIANGLESTRIP;
````


## -struct-fields




### -field wVStart

Specifies the index to the vertex buffer containing coordinate data for the initial vertex of the triangle strip.


## -remarks



One D3DHAL_DP2TRIANGLESTRIP structure follows the D3DHAL_DP2COMMAND structure in the command buffer.


<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should process a total of (<b>wPrimitiveCount</b> + 2) vertices from the vertex buffer. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The triangle edges in a triangle strip are rendered in this order: (<b>wV[</b>0<b>]</b>, <b>wV[</b>1<b>]</b>, <b>wV[</b>2<b>]</b>), (<b>wV[</b>1<b>]</b>, <b>wV[</b>3<b>]</b>, <b>wV[</b>2<b>]</b>), (<b>wV[</b>2<b>]</b>, <b>wV[</b>3<b>]</b>, <b>wV[</b>4<b>]</b>), (<b>wV[</b>3<b>]</b>, <b>wV[</b>5<b>]</b>, <b>wV[</b>4<b>]</b>),...

For the last triangle in the triangle strip, however, the edges are rendered in different orders when <b>wPrimitiveCount</b>t is odd and when it is even.

<ul>
<li>
When <b>wPrimitiveCount</b> is an odd number, the last triangle's edges are rendered in this order: (<b>wV[wPrimitiveCount</b> - 1<b>]</b>, <b>wV[wPrimitiveCount]</b>, <b>wV[wPrimitiveCount </b>+ 1<b>]</b>).

</li>
<li>
When <b>wPrimitiveCount</b> is an even number, the last triangle's edges are rendered in this order: (<b>wV[wPrimitiveCount</b>- 1<b>]</b>, <b>wV[wPrimitiveCount</b> + 1<b>]</b>, <b>wV[wPrimitiveCount</b>).

</li>
</ul>
The following figure shows a portion of a sample command buffer containing a D3DDP2OP_TRIANGLESTRIP command and one D3DHAL_DP2TRIANGLESTRIP structure. The driver should process five vertices from the vertex buffer, rendering a strip of three triangles defined by (v[0], v[1], v[2]), (v[1], v[3], v[2]), (v[2], v[3], v[4]).

<img alt="Figure showing a command buffer with a D3DDP2OP_TRIANGLESTRIP command and one D3DHAL_DP2TRIANGLESTRIP structure" src="images/dp2trist.png"/>



## -see-also

D3DDP2OP_TRIANGLESTRIP



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2TRIANGLESTRIP structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

