---
UID: NS:d3dumddi._D3DDDIARG_DRAWPRIMITIVE
title: _D3DDDIARG_DRAWPRIMITIVE (d3dumddi.h)
description: The D3DDDIARG_DRAWPRIMITIVE structure describes a nonindexed primitive to draw.
old-location: display\d3dddiarg_drawprimitive.htm
tech.root: display
ms.assetid: b5c3a750-7ccb-42ab-9648-17c43e390ec8
ms.date: 05/10/2018
keywords: ["D3DDDIARG_DRAWPRIMITIVE structure"]
ms.keywords: D3DDDIARG_DRAWPRIMITIVE, D3DDDIARG_DRAWPRIMITIVE structure [Display Devices], UMDisplayDriver_param_Structs_19d7b078-8ea3-4b3a-982a-1163643df142.xml, _D3DDDIARG_DRAWPRIMITIVE, d3dumddi/D3DDDIARG_DRAWPRIMITIVE, display.d3dddiarg_drawprimitive
f1_keywords:
 - "d3dumddi/D3DDDIARG_DRAWPRIMITIVE"
 - "D3DDDIARG_DRAWPRIMITIVE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_DRAWPRIMITIVE
targetos: Windows
req.typenames: D3DDDIARG_DRAWPRIMITIVE
---

# _D3DDDIARG_DRAWPRIMITIVE structure


## -description


The D3DDDIARG_DRAWPRIMITIVE structure describes a nonindexed primitive to draw. 


## -struct-fields




### -field PrimitiveType

[in] A D3DPRIMITIVETYPE-typed value that indicates the type of primitive to draw. This member can be one of the following values: D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP, or D3DPT_TRIANGLEFAN. For more information about D3DPRIMITIVETYPE, see the Microsoft Windows SDK documentation.


### -field VStart

[in] The index (into each active vertex stream) of the vertex elements to start drawing with. Vertex data should be read from the current vertex streams (those that are referenced by the current vertex shader).


### -field PrimitiveCount

[in] The number of triangles, lines, or points to draw for the given primitive. 


## -remarks



The Microsoft Direct3D runtime does not transform the vertex data before passing a pointer to the description of the vertex data in the <i>pData</i> parameter in a call to the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_drawprimitive">DrawPrimitive</a> function. 

When the runtime specifies triangle-edge flags in the value that is pointed to by the <i>pFlagBuffer</i> parameter in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_drawprimitive">DrawPrimitive</a> call, the runtime also specifies to draw one or more triangles (that is, the runtime specifies the D3DPT_TRIANGLEFAN value in the <b>PrimitiveType</b> member and from 0x00000001 to 0xFFFFFFFF in the <b>PrimitiveCount</b> member of D3DDDIARG_DRAWPRIMITIVE that is pointed to by the <i>pData</i> parameter in the <b>DrawPrimitive</b> call).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_drawprimitive">DrawPrimitive</a>
 

 

