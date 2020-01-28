---
UID: NC:d3dumddi.PFND3DDDI_DRAWPRIMITIVE
title: PFND3DDDI_DRAWPRIMITIVE (d3dumddi.h)
description: The DrawPrimitive function draws nonindexed primitives in which the Microsoft Direct3D runtime has not transformed the vertex data.
old-location: display\drawprimitive.htm
tech.root: display
ms.assetid: 1a6de2b0-cab0-4fcf-be1b-a8cc1c1f79e9
ms.date: 05/10/2018
ms.keywords: DrawPrimitive, DrawPrimitive callback function [Display Devices], PFND3DDDI_DRAWPRIMITIVE, PFND3DDDI_DRAWPRIMITIVE callback, UserModeDisplayDriver_Functions_c433d1f5-68ca-4461-a409-4353d8a581d8.xml, d3dumddi/DrawPrimitive, display.drawprimitive
f1_keywords:
 - "d3dumddi/DrawPrimitive"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
- UserDefined
api_location:
- D3dumddi.h
api_name:
- DrawPrimitive
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DRAWPRIMITIVE callback function


## -description


The <b>DrawPrimitive</b> function draws nonindexed primitives in which the Microsoft Direct3D runtime has not transformed the vertex data.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_drawprimitive">D3DDDIARG_DRAWPRIMITIVE</a> structure that describes the primitive to draw.

### -param Arg3

*pFlagBuffer* [in]

A pointer to a 32-bit value that contains triangle-edge flags, which are used only during line-fill mode. The first three bits (0/1/2) of the 32-bit value specify how the three edges of the corresponding triangles are rendered. If a bit is set to 1, its associated triangle edge is rendered; otherwise, the edge is not rendered.

If the pointer is <b>NULL</b>, the user-mode display driver should use its fast path to draw primitives. 


## -returns



<b>DrawPrimitive</b> returns S_OK or an appropriate error result if the primitive is not successfully drawn.




## -remarks



When the Microsoft Direct3D runtime specifies triangle-edge flags in the value that the <i>pFlagBuffer</i> parameter points to, the runtime also specifies to draw one or more triangles (that is, the runtime specifies the D3DPT_TRIANGLEFAN value in the <b>PrimitiveType</b> member and from 0x00000001 to 0xFFFFFFFF in the <b>PrimitiveCount</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_drawprimitive">D3DDDIARG_DRAWPRIMITIVE</a> structure that the <i>pData</i> parameter points to).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_drawprimitive">D3DDDIARG_DRAWPRIMITIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
 

 

