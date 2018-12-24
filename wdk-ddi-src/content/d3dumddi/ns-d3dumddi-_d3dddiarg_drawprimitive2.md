---
UID: NS:d3dumddi._D3DDDIARG_DRAWPRIMITIVE2
title: "_D3DDDIARG_DRAWPRIMITIVE2"
description: The D3DDDIARG_DRAWPRIMITIVE2 structure describes a nonindexed primitive to draw.
old-location: display\d3dddiarg_drawprimitive2.htm
tech.root: display
ms.assetid: fb9668a8-54b5-4d07-8682-af2b593308a5
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_DRAWPRIMITIVE2, D3DDDIARG_DRAWPRIMITIVE2 structure [Display Devices], UMDisplayDriver_param_Structs_76f6de24-fe57-4907-a84a-692ab80e2dab.xml, _D3DDDIARG_DRAWPRIMITIVE2, d3dumddi/D3DDDIARG_DRAWPRIMITIVE2, display.d3dddiarg_drawprimitive2
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
-	D3DDDIARG_DRAWPRIMITIVE2
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DRAWPRIMITIVE2
---

# _D3DDDIARG_DRAWPRIMITIVE2 structure


## -description


The D3DDDIARG_DRAWPRIMITIVE2 structure describes a nonindexed primitive to draw. 


## -struct-fields




### -field PrimitiveType

[in] A D3DPRIMITIVETYPE-typed value that indicates the type of primitive to draw. This member can be one of the following values: D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP, or D3DPT_TRIANGLEFAN. For more information about D3DPRIMITIVETYPE, see the Microsoft Windows SDK documentation.


### -field FirstVertexOffset

[in] The offset, in bytes, in stream zero of the vertex data. This member differs from the <b>VStart</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543057">D3DDDIARG_DRAWPRIMITIVE</a> structure that is used with the <a href="https://msdn.microsoft.com/1a6de2b0-cab0-4fcf-be1b-a8cc1c1f79e9">DrawPrimitive</a> function. In <b>VStart</b>, the start of the vertex data in the vertex stream is specified by a vertex index rather than an actual byte offset.


### -field PrimitiveCount

[in] The number of triangles, lines, or points to draw for the given primitive. 


## -remarks



The Microsoft Direct3D runtime transforms the vertex data before passing a pointer to the description of the vertex data in the <i>pData</i> parameter in a call to the user-mode display driver's <a href="https://msdn.microsoft.com/a81080f0-fbb3-4616-9324-642b60befcb3">DrawPrimitive2</a> function. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543057">D3DDDIARG_DRAWPRIMITIVE</a>



<a href="https://msdn.microsoft.com/a81080f0-fbb3-4616-9324-642b60befcb3">DrawPrimitive2</a>
 

 

