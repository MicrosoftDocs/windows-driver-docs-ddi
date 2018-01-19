---
UID: NS:d3dhal._D3DHAL_DP2DRAWPRIMITIVE2
title: _D3DHAL_DP2DRAWPRIMITIVE2
author: windows-driver-content
description: DirectX 8.0 and later versions only. D3DHAL_DRAWPRIMITIVE2 is parsed from the command buffer by the D3dDrawPrimitives2 callback when the D3DHAL_DP2COMMAND structure's bCommand member is set to D3DDP2OP_DRAWPRIMITIVE2, and is used to render a primitive.
old-location: display\d3dhal_dp2drawprimitive2.htm
old-project: display
ms.assetid: de73a814-2406-4976-ae12-909ed820586c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DHAL_DP2DRAWPRIMITIVE2, D3DHAL_DP2DRAWPRIMITIVE2, *LPD3DHAL_DP2DRAWPRIMITIVE2
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
req.alt-api: D3DHAL_DP2DRAWPRIMITIVE2
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
req.typenames: D3DHAL_DP2DRAWPRIMITIVE2
---

# _D3DHAL_DP2DRAWPRIMITIVE2 structure



## -description

   DirectX 8.0 and later versions only.
   

D3DHAL_DRAWPRIMITIVE2 is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_DRAWPRIMITIVE2, and is used to render a primitive.



## -syntax

````
typedef struct _D3DHAL_DP2DRAWPRIMITIVE2 {
  D3DPRIMITIVETYPE primType;
  DWORD            FirstVertexOffset;
  DWORD            PrimitiveCount;
} D3DHAL_DP2DRAWPRIMITIVE2, *LPD3DHAL_DP2DRAWPRIMITIVE2;
````


## -struct-fields

### -field primType

Specifies the type of primitive to draw (one of D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP or D3DPT_TRIANGLEFAN).


### -field FirstVertexOffset

Specifies the offset, in bytes, in stream zero of the vertex data. This is in contrast to D3DDP2OP_DRAWPRIMITIVE where the start of the vertex data in the vertex stream is specified by a vertex index rather than an actual byte offset.


### -field PrimitiveCount

Specifies the number of triangles, lines or points to draw for the given primitive.


## -remarks
The vertex data has been transformed by the runtime.


## -see-also
<dl>
<dt>D3DDP2OP_DRAWPRIMITIVE</dt>
<dt>D3DDP2OP_DRAWPRIMITIVE2</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2drawprimitive.md">D3DHAL_DP2DRAWPRIMITIVE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2DRAWPRIMITIVE2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

