---
UID: NC:d3dumddi.PFND3DDDI_DRAWPRIMITIVE2
title: PFND3DDDI_DRAWPRIMITIVE2 (d3dumddi.h)
description: The DrawPrimitive2 function draws nonindexed primitives in which the Microsoft Direct3D runtime has transformed the vertex data.
old-location: display\drawprimitive2.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DRAWPRIMITIVE2 callback function"]
ms.keywords: DrawPrimitive2, DrawPrimitive2 callback function [Display Devices], PFND3DDDI_DRAWPRIMITIVE2, PFND3DDDI_DRAWPRIMITIVE2 callback, UserModeDisplayDriver_Functions_5c08f7ff-b74c-4389-9b35-2f24f9468b5d.xml, d3dumddi/DrawPrimitive2, display.drawprimitive2
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_DRAWPRIMITIVE2
 - d3dumddi/PFND3DDDI_DRAWPRIMITIVE2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_DRAWPRIMITIVE2
---

# PFND3DDDI_DRAWPRIMITIVE2 callback function


## -description

The <b>DrawPrimitive2</b> function draws nonindexed primitives in which the Microsoft Direct3D runtime has transformed the vertex data.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param unnamedParam2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_drawprimitive2">D3DDDIARG_DRAWPRIMITIVE2</a> structure that describes the primitive to draw.

## -returns

<b>DrawPrimitive2</b> returns S_OK or an appropriate error result if the primitive is not successfully drawn.

## -remarks

Stream zero contains transform vertices and is the only stream that should be accessed.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_drawprimitive2">D3DDDIARG_DRAWPRIMITIVE2</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

