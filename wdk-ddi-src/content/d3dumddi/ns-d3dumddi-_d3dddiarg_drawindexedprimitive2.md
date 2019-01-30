---
UID: NS:d3dumddi._D3DDDIARG_DRAWINDEXEDPRIMITIVE2
title: "_D3DDDIARG_DRAWINDEXEDPRIMITIVE2" (d3dumddi.h)
description: The D3DDDIARG_DRAWINDEXEDPRIMITIVE2 structure describes an indexed primitive to draw.
old-location: display\d3dddiarg_drawindexedprimitive2.htm
tech.root: display
ms.assetid: 91bf3d1d-5be2-4790-9e6d-07db5eed4f06
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_DRAWINDEXEDPRIMITIVE2, D3DDDIARG_DRAWINDEXEDPRIMITIVE2 structure [Display Devices], UMDisplayDriver_param_Structs_464c958b-5ca2-4e21-9d1f-a7c32cb49295.xml, _D3DDDIARG_DRAWINDEXEDPRIMITIVE2, d3dumddi/D3DDDIARG_DRAWINDEXEDPRIMITIVE2, display.d3dddiarg_drawindexedprimitive2
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dumddi.h
api_name:
-	D3DDDIARG_DRAWINDEXEDPRIMITIVE2
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DRAWINDEXEDPRIMITIVE2
---

# _D3DDDIARG_DRAWINDEXEDPRIMITIVE2 structure


## -description


The D3DDDIARG_DRAWINDEXEDPRIMITIVE2 structure describes an indexed primitive to draw. 


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



The Microsoft Direct3D runtime transforms the index data before passing a pointer to the description of the index data in the <i>pData</i> parameter in a call to the user-mode display driver's <a href="https://msdn.microsoft.com/f12af70c-a6f2-42da-be62-1cfeb90b6239">DrawIndexedPrimitive2</a> function. 

When the runtime specifies triangle-edge flags in the value that is pointed to by the <i>pFlagBuffer</i> parameter in the <a href="https://msdn.microsoft.com/f12af70c-a6f2-42da-be62-1cfeb90b6239">DrawIndexedPrimitive2</a> call, the runtime also specifies to draw only one triangle (that is, the runtime specifies the D3DPT_TRIANGLELIST value in the <b>PrimitiveType</b> member and 0x00000001 in the <b>PrimitiveCount</b> member of D3DDDIARG_DRAWINDEXEDPRIMITIVE2 that is pointed to by the <i>pData</i> parameter in the <b>DrawIndexedPrimitive2</b> call).




## -see-also




<a href="https://msdn.microsoft.com/f12af70c-a6f2-42da-be62-1cfeb90b6239">DrawIndexedPrimitive2</a>
 

 

