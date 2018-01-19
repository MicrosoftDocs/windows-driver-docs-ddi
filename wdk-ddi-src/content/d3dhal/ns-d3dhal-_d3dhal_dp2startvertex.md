---
UID: NS:d3dhal._D3DHAL_DP2STARTVERTEX
title: _D3DHAL_DP2STARTVERTEX
author: windows-driver-content
description: A D3DHAL_DP2STARTVERTEX structure follows certain D3DHAL_DP2COMMAND structures in the command buffer, and indicates the offset in the vertex buffer for the first vertex to use in D3dDrawPrimitives2.
old-location: display\d3dhal_dp2startvertex.htm
old-project: display
ms.assetid: 302ed135-9fde-4101-876f-1f70bed501b0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DHAL_DP2STARTVERTEX, D3DHAL_DP2STARTVERTEX, *LPD3DHAL_DP2STARTVERTEX
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
req.alt-api: D3DHAL_DP2STARTVERTEX
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
req.typenames: D3DHAL_DP2STARTVERTEX, *LPD3DHAL_DP2STARTVERTEX
---

# _D3DHAL_DP2STARTVERTEX structure



## -description
A D3DHAL_DP2STARTVERTEX structure follows certain <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structures in the command buffer, and indicates the offset in the vertex buffer for the first vertex to use in <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.



## -syntax

````
typedef struct _D3DHAL_DP2STARTVERTEX {
  WORD wVStart;
} D3DHAL_DP2STARTVERTEX, *LPD3DHAL_DP2STARTVERTEX;
````


## -struct-fields

### -field wVStart

Specifies an additional offset to be added to any index used for determining the location of vertices in the vertex buffer (in the case of indexed primitives).


## -remarks
A D3DHAL_DP2STARTVERTEX structure follows a D3DHAL_DP2COMMAND structure in the command buffer when the <b>bCommand</b> member of D3DHAL_DP2COMMAND is one of the following values:

D3DDP2OP_INDEXEDLINELIST2

D3DDP2OP_INDEXEDLINESTRIP

D3DDP2OP_INDEXEDTRIANGLELIST2

D3DDP2OP_INDEXEDTRIANGLESTRIP

D3DDP2OP_INDEXEDTRIANGLEFAN

The first vertex of such primitives is located (<b>wVStart</b> + <b>dwVertexOffset</b>) bytes from the beginning of the vertex buffer, where <b>dwVertexOffset</b> is a member of <a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a>.


## -see-also
<dl>
<dt>D3DDP2OP_INDEXEDLINELIST2</dt>
<dt>D3DDP2OP_INDEXEDLINESTRIP</dt>
<dt>D3DDP2OP_INDEXEDTRIANGLELIST2</dt>
<dt>D3DDP2OP_INDEXEDTRIANGLESTRIP</dt>
<dt>D3DDP2OP_INDEXEDTRIANGLEFAN</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_drawprimitives2data.md">D3DHAL_DRAWPRIMITIVES2DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2STARTVERTEX structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

