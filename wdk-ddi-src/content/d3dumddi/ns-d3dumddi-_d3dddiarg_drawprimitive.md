---
UID: NS:d3dumddi._D3DDDIARG_DRAWPRIMITIVE
title: "_D3DDDIARG_DRAWPRIMITIVE"
author: windows-driver-content
description: The D3DDDIARG_DRAWPRIMITIVE structure describes a nonindexed primitive to draw.
old-location: display\d3dddiarg_drawprimitive.htm
old-project: display
ms.assetid: b5c3a750-7ccb-42ab-9648-17c43e390ec8
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, A, D, D3DDDIARG_DRAWPRIMITIVE, D3DDDIARG_DRAWPRIMITIVE structure [Display Devices], E, G, I, M, P, R, T, UMDisplayDriver_param_Structs_19d7b078-8ea3-4b3a-982a-1163643df142.xml, V, W, _, _D3DDDIARG_DRAWPRIMITIVE, d3dumddi/D3DDDIARG_DRAWPRIMITIVE, display.d3dddiarg_drawprimitive"
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
-	d3dumddi.h
apiname:
-	D3DDDIARG_DRAWPRIMITIVE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DRAWPRIMITIVE
---

# _D3DDDIARG_DRAWPRIMITIVE structure


## -description


The D3DDDIARG_DRAWPRIMITIVE structure describes a nonindexed primitive to draw. 


## -syntax


````
typedef struct _D3DDDIARG_DRAWPRIMITIVE {
  D3DPRIMITIVETYPE PrimitiveType;
  UINT             VStart;
  UINT             PrimitiveCount;
} D3DDDIARG_DRAWPRIMITIVE;
````


## -struct-fields




### -field PrimitiveType

[in] A D3DPRIMITIVETYPE-typed value that indicates the type of primitive to draw. This member can be one of the following values: D3DPT_POINTLIST, D3DPT_LINELIST, D3DPT_LINESTRIP, D3DPT_TRIANGLELIST, D3DPT_TRIANGLESTRIP, or D3DPT_TRIANGLEFAN. For more information about D3DPRIMITIVETYPE, see the Microsoft Windows SDK documentation.


### -field VStart

[in] The index (into each active vertex stream) of the vertex elements to start drawing with. Vertex data should be read from the current vertex streams (those that are referenced by the current vertex shader).


### -field PrimitiveCount

[in] The number of triangles, lines, or points to draw for the given primitive. 


## -remarks



The Microsoft Direct3D runtime does not transform the vertex data before passing a pointer to the description of the vertex data in the <i>pData</i> parameter in a call to the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive.md">DrawPrimitive</a> function. 

When the runtime specifies triangle-edge flags in the value that is pointed to by the <i>pFlagBuffer</i> parameter in the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive.md">DrawPrimitive</a> call, the runtime also specifies to draw one or more triangles (that is, the runtime specifies the D3DPT_TRIANGLEFAN value in the <b>PrimitiveType</b> member and from 0x00000001 to 0xFFFFFFFF in the <b>PrimitiveCount</b> member of D3DDDIARG_DRAWPRIMITIVE that is pointed to by the <i>pData</i> parameter in the <b>DrawPrimitive</b> call).




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive.md">DrawPrimitive</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DRAWPRIMITIVE structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

