---
UID: NS:d3dhal._D3DHAL_DP2DRAWINDEXEDPRIMITIVE2
title: "_D3DHAL_DP2DRAWINDEXEDPRIMITIVE2"
author: windows-driver-content
description: DirectX 8.0 and later versions only.
old-location: display\d3dhal_dp2drawindexedprimitive2.htm
old-project: display
ms.assetid: 0376a2ce-2f1f-4515-b80a-2ecf0941d7d3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE2, D3DHAL_DP2DRAWINDEXEDPRIMITIVE2, D3DHAL_DP2DRAWINDEXEDPRIMITIVE2 structure [Display Devices], LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE2, LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE2 structure pointer [Display Devices], _D3DHAL_DP2DRAWINDEXEDPRIMITIVE2, d3dhal/D3DHAL_DP2DRAWINDEXEDPRIMITIVE2, d3dhal/LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE2, d3dstrct_43a90135-93f4-4304-9967-b4d7b6616198.xml, display.d3dhal_dp2drawindexedprimitive2"
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
-	D3DHAL_DP2DRAWINDEXEDPRIMITIVE2
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2DRAWINDEXEDPRIMITIVE2
---

# _D3DHAL_DP2DRAWINDEXEDPRIMITIVE2 structure


## -description



   DirectX 8.0 and later versions only.
   

D3DHAL_DRAWINDEXEDPRIMITIVE2 is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_DRAWINDEXEDPRIMITIVE2, and is used to render a primitive using vertex indices.


## -syntax


````
typedef struct _D3DHAL_DP2DRAWINDEXEDPRIMITIVE2 {
  D3DPRIMITIVETYPE primType;
  INT              BaseVertexOffset;
  DWORD            MinIndex;
  DWORD            NumVertices;
  DWORD            StartIndexOffset;
  DWORD            PrimitiveCount;
} D3DHAL_DP2DRAWINDEXEDPRIMITIVE2, *LPD3DHAL_DP2DRAWINDEXEDPRIMITIVE2;
````


## -struct-fields




### -field primType

Specifies the type of primitive to draw (one of D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP or D3DPT_TRIANGLEFAN).


### -field BaseVertexOffset

Specifies the offset that should be added to each vertex in vertex stream 0 by the various primitives to determine the actual vertex in vertex stream 0. This offset could be negative, but when an index is added to the offset the result is positive.


### -field MinIndex

Specifies the minimum index of a range of vertices that are potentially accessed by the primitives to be drawn and, therefore, which vertices should be processed.


### -field NumVertices

Specifies the number of vertices in a range that are potentially accessed by the primitives to be drawn and, therefore, which vertices should be processed.


### -field StartIndexOffset

Specifies the offset of the first index in the index buffer from which indices are read to draw the primitives.


### -field PrimitiveCount

Specifies the number of triangles, lines or points to draw for the given primitive.


## -remarks



The vertex data has been transformed by the runtime.

As with vertices, the actual indices to use are not passed with the token data, but rather should be read from the currently selected index buffer. See <a href="https://msdn.microsoft.com/5bf7dc12-d988-4194-a81f-52c9c5356610">Index Buffers</a> for more details.




## -see-also

<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2drawindexedprimitive2.md">D3DHAL_DP2DRAWINDEXEDPRIMITIVE2</a>



D3DDP2OP_DRAWINDEXEDPRIMITIVE2



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2DRAWINDEXEDPRIMITIVE2 structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

