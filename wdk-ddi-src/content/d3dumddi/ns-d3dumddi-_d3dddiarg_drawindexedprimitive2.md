---
UID: NS:d3dumddi._D3DDDIARG_DRAWINDEXEDPRIMITIVE2
title: _D3DDDIARG_DRAWINDEXEDPRIMITIVE2
author: windows-driver-content
description: The D3DDDIARG_DRAWINDEXEDPRIMITIVE2 structure describes an indexed primitive to draw.
old-location: display\d3dddiarg_drawindexedprimitive2.htm
old-project: display
ms.assetid: 91bf3d1d-5be2-4790-9e6d-07db5eed4f06
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIARG_DRAWINDEXEDPRIMITIVE2, D3DDDIARG_DRAWINDEXEDPRIMITIVE2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_DRAWINDEXEDPRIMITIVE2
req.alt-loc: d3dumddi.h
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
req.typenames: D3DDDIARG_DRAWINDEXEDPRIMITIVE2
---

# _D3DDDIARG_DRAWINDEXEDPRIMITIVE2 structure



## -description
The D3DDDIARG_DRAWINDEXEDPRIMITIVE2 structure describes an indexed primitive to draw. 



## -syntax

````
typedef struct _D3DDDIARG_DRAWINDEXEDPRIMITIVE2 {
  D3DPRIMITIVETYPE PrimitiveType;
  INT              BaseVertexOffset;
  UINT             MinIndex;
  UINT             NumVertices;
  UINT             StartIndexOffset;
  UINT             PrimitiveCount;
} D3DDDIARG_DRAWINDEXEDPRIMITIVE2;
````


## -struct-fields

### -field PrimitiveType

[in] A D3DPRIMITIVETYPE-typed value that indicates the type of primitive to draw. This member can be one of the following values: D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP, or D3DPT_TRIANGLEFAN. For more information about D3DPRIMITIVETYPE, see the Microsoft Windows SDK documentation.


### -field BaseVertexOffset

[in] The offset that should be added to each vertex in vertex stream 0 by the various primitives to determine the actual vertex in vertex stream 0. This offset could be negative, but when an index is added to the offset, the result is positive. 


### -field MinIndex

[in] The minimum index of a range of vertices that are potentially accessed by the primitives to be drawn and, therefore, which vertices should be processed.


### -field NumVertices

[in] The number of vertices in a range that are potentially accessed by the primitives to be drawn and, therefore, which vertices should be processed.


### -field StartIndexOffset

[in] The offset of the first index in the index buffer from which indices are read to draw the primitives.


### -field PrimitiveCount

[in] The number of triangles, lines, or points to draw for the given primitive. 


## -remarks
The Microsoft Direct3D runtime transforms the index data before passing a pointer to the description of the index data in the <i>pData</i> parameter in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawindexedprimitive2.md">DrawIndexedPrimitive2</a> function. 

When the runtime specifies triangle-edge flags in the value that is pointed to by the <i>pFlagBuffer</i> parameter in the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawindexedprimitive2.md">DrawIndexedPrimitive2</a> call, the runtime also specifies to draw only one triangle (that is, the runtime specifies the D3DPT_TRIANGLELIST value in the <b>PrimitiveType</b> member and 0x00000001 in the <b>PrimitiveCount</b> member of D3DDDIARG_DRAWINDEXEDPRIMITIVE2 that is pointed to by the <i>pData</i> parameter in the <b>DrawIndexedPrimitive2</b> call).


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawindexedprimitive2.md">DrawIndexedPrimitive2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DRAWINDEXEDPRIMITIVE2 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

