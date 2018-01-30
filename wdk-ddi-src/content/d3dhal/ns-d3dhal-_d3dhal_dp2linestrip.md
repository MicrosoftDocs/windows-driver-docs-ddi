---
UID: NS:d3dhal._D3DHAL_DP2LINESTRIP
title: "_D3DHAL_DP2LINESTRIP"
author: windows-driver-content
description: One D3DHAL_DP2LINESTRIP structure is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_LINESTRIP, and is used to render the specified connected line segments.
old-location: display\d3dhal_dp2linestrip.htm
old-project: display
ms.assetid: 1f893474-c132-4843-985a-5ef1d0d8f32d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dstrct_d49daf52-1228-463a-8db5-3802da2fc787.xml, display.d3dhal_dp2linestrip, LPD3DHAL_DP2LINESTRIP structure pointer [Display Devices], *LPD3DHAL_DP2LINESTRIP, d3dhal/LPD3DHAL_DP2LINESTRIP, D3DHAL_DP2LINESTRIP, d3dhal/D3DHAL_DP2LINESTRIP, D3DHAL_DP2LINESTRIP structure [Display Devices], _D3DHAL_DP2LINESTRIP, LPD3DHAL_DP2LINESTRIP
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
-	D3DHAL_DP2LINESTRIP
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2LINESTRIP, *LPD3DHAL_DP2LINESTRIP
---

# _D3DHAL_DP2LINESTRIP structure


## -description


One D3DHAL_DP2LINESTRIP structure is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_LINESTRIP, and is used to render the specified connected line segments.


## -syntax


````
typedef struct _D3DHAL_DP2LINESTRIP {
  WORD wVStart;
} D3DHAL_DP2LINESTRIP, *LPD3DHAL_DP2LINESTRIP;
````


## -struct-fields




### -field wVStart

Specifies the index into the vertex buffer containing coordinate data for the initial vertex of the line strip.


## -remarks


One D3DHAL_DP2LINESTRIP structure follows the D3DHAL_DP2COMMAND structure in the command buffer.


<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should sequentially process a total of (<b>wPrimitiveCount</b> + 1) vertices from the vertex buffer. Starting from the vertex buffer offset, the sequence of lines rendered is (<b>wVStart</b>, <b>wVStart</b> + 1), (<b>wVStart</b> + 1, <b>wVStart</b> + 2), (<b>wVStart</b> + 2, <b>wVStart</b> + 3), ..., (<b>wVStart</b> + (<b>wPrimitiveCount</b> - 1), <b>wVStart</b> + <b>wPrimitiveCount</b>). The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_LINESTRIP command and one D3DHAL_DP2LINESTRIP structure. The driver should draw three connected lines using the following four vertices from the vertex buffer: (v[4], v[5]), (v[5], v[6]), (v[6], v[7]).
<img alt="Figure showing a command buffer with a D3DDP2OP_LINESTRIP command and one D3DHAL_DP2LINESTRIP structure" src="images/dp2lstr.png"/>


## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>

D3DDP2OP_LINESTRIP

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2LINESTRIP structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

