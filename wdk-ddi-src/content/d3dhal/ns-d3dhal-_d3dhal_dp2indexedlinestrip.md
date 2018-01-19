---
UID: NS:d3dhal._D3DHAL_DP2INDEXEDLINESTRIP
title: _D3DHAL_DP2INDEXEDLINESTRIP
author: windows-driver-content
description: D3DHAL_DP2INDEXEDLINESTRIP is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_INDEXEDLINESTRIP, and is used to render a sequence of connected line segments using vertex indices.
old-location: display\d3dhal_dp2indexedlinestrip.htm
old-project: display
ms.assetid: 92809162-c39e-4dbb-9ab1-a5b6535d5beb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DHAL_DP2INDEXEDLINESTRIP, D3DHAL_DP2INDEXEDLINESTRIP, *LPD3DHAL_DP2INDEXEDLINESTRIP
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
req.alt-api: D3DHAL_DP2INDEXEDLINESTRIP
req.alt-loc: d3dhal.h
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
req.typenames: D3DHAL_DP2INDEXEDLINESTRIP, *LPD3DHAL_DP2INDEXEDLINESTRIP
---

# _D3DHAL_DP2INDEXEDLINESTRIP structure



## -description
D3DHAL_DP2INDEXEDLINESTRIP is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_INDEXEDLINESTRIP, and is used to render a sequence of connected line segments using vertex indices.



## -syntax

````
typedef struct _D3DHAL_DP2INDEXEDLINESTRIP {
  WORD wV[2];
} D3DHAL_DP2INDEXEDLINESTRIP, *LPD3DHAL_DP2INDEXEDLINESTRIP;
````


## -struct-fields

### -field wV

Specifies the indexes into the vertex buffer from which the driver obtains coordinate data for the vertices making up the line strip. 

Although this member has only enough space to hold two indexes, this array of indexes should be treated as a variable-sized array with (<b>wPrimitiveCount</b>+ 1) elements. (<b>wPrimitiveCount</b> is a member of the D3DHAL_DP2COMMAND structure.)


## -remarks
Indexed line strips rendered with vertex buffers are specified using D3DHAL_DP2INDEXEDLINESTRIP. The number of line segments to process is specified by the <b>wPrimitiveCount</b> member of D3DHAL_DP2COMMAND. The sequence of line segments rendered is: (<b>wV[</b>0<b>]</b>, <b>wV[</b>1<b>]</b>), (<b>wV[</b>1<b>]</b>, <b>wV[</b>2<b>]</b>), (<b>wV[</b>2<b>]</b>, <b>wV[</b>3<b>]</b>), ..., (<b>wVStart[wPrimitiveCount</b> -1<b>]</b>, <b>wVStart[wPrimitiveCount]</b>). 


<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> should process (<b>wPrimitiveCount</b>+1) indexes from the command buffer, in effect processing <b>wPrimitiveCount</b> D3DHAL_DP2INDEXEDLINESTRIP structures. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure.

A <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2startvertex.md">D3DHAL_DP2STARTVERTEX</a> structure immediately follows the command in the command buffer. The vertex buffer indexes are relative to the vertex buffer offset specified by the <b>dwVertexOffset</b> member of the <a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a> structure plus the base offset obtained from the <b>wVStart</b> member of the D3DHAL_DP2STARTVERTEX structure.

The following figure shows a portion of a sample command buffer containing a D3DDP2OP_INDEXEDLINESTRIP command, a D3DHAL_DP2STARTVERTEX offset, and a list of D3DHAL_DP2INDEXEDLINESTRIP structures. The driver should process four vertices from the vertex buffer, rendering three connected line segments defined by (v[8], v[4]), (v[4], v[7]), (v[7], v[6]).


## -see-also
<dl>
<dt>D3DDP2OP_INDEXEDLINESTRIP</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2startvertex.md">D3DHAL_DP2STARTVERTEX</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2INDEXEDLINESTRIP structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

