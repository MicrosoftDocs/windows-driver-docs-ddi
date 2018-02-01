---
UID: NS:d3dhal._D3DHAL_DP2POINTS
title: "_D3DHAL_DP2POINTS"
author: windows-driver-content
description: One or more D3DHAL_DP2POINTS structures are parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_POINTS, and are used to render the specified points.
old-location: display\d3dhal_dp2points.htm
old-project: display
ms.assetid: 9987ed83-7aa1-4e07-a85b-26607000ecba
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DHAL_DP2POINTS structure [Display Devices], d3dstrct_ab7299b5-74b9-43bb-8784-6c1249e23f2f.xml, d3dhal/LPD3DHAL_DP2POINTS, LPD3DHAL_DP2POINTS, D3DHAL_DP2POINTS, *LPD3DHAL_DP2POINTS, LPD3DHAL_DP2POINTS structure pointer [Display Devices], d3dhal/D3DHAL_DP2POINTS, display.d3dhal_dp2points, _D3DHAL_DP2POINTS
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
-	D3DHAL_DP2POINTS
product: Windows
targetos: Windows
req.typenames: "*LPD3DHAL_DP2POINTS, D3DHAL_DP2POINTS"
---

# _D3DHAL_DP2POINTS structure


## -description


One or more D3DHAL_DP2POINTS structures are parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_POINTS, and are used to render the specified points.


## -syntax


````
typedef struct _D3DHAL_DP2POINTS {
  WORD wCount;
  WORD wVStart;
} D3DHAL_DP2POINTS, *LPD3DHAL_DP2POINTS;
````


## -struct-fields




### -field wCount

Specifies the number of points to render.


### -field wVStart

Specifies the index into the vertex buffer containing coordinate data for the initial point.


## -remarks



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should process <b>wPrimitiveCount</b> D3DHAL_DP2POINTS structures from the command buffer. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

For each D3DHAL_DP2POINTS structure, <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should sequentially process <b>wCount</b> vertices from the vertex buffer. Starting from the vertex buffer offset, the sequence of points rendered is <b>wVStart</b>, (<b>wVStart</b>+1), ..., (<b>wVStart</b>+(<b>wCount</b>-1)).

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_POINTS command and two D3DHAL_DP2POINTS structures. The driver should draw a total of seven points using the following vertices from the vertex buffer: v[2], v[3], v[4], v[7], v[8], v[9], v[10].
<img alt="Figure showing a command buffer with a D3DDP2OP_POINTS command and two D3DHAL_DP2POINTS structures" src="images/dp2pnts.png"/>


## -see-also

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>

D3DDP2OP_POINTS

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2POINTS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

