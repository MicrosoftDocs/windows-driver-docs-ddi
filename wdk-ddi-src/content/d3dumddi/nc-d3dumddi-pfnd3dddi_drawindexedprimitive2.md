---
UID: NC:d3dumddi.PFND3DDDI_DRAWINDEXEDPRIMITIVE2
title: PFND3DDDI_DRAWINDEXEDPRIMITIVE2 (d3dumddi.h)
description: The DrawIndexedPrimitive2 function draws indexed primitives that the Microsoft Direct3D runtime has transformed the index data in.
old-location: display\drawindexedprimitive2.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DRAWINDEXEDPRIMITIVE2 callback function"]
ms.keywords: DrawIndexedPrimitive2, DrawIndexedPrimitive2 callback function [Display Devices], PFND3DDDI_DRAWINDEXEDPRIMITIVE2, PFND3DDDI_DRAWINDEXEDPRIMITIVE2 callback, UserModeDisplayDriver_Functions_55bb1ac5-49e3-428b-9737-ffe0577e6bba.xml, d3dumddi/DrawIndexedPrimitive2, display.drawindexedprimitive2
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
 - PFND3DDDI_DRAWINDEXEDPRIMITIVE2
 - d3dumddi/PFND3DDDI_DRAWINDEXEDPRIMITIVE2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_DRAWINDEXEDPRIMITIVE2
---

# PFND3DDDI_DRAWINDEXEDPRIMITIVE2 callback function


## -description

The <b>DrawIndexedPrimitive2</b> function draws indexed primitives that the Microsoft Direct3D runtime has transformed the index data in.

## -parameters

### -param hDevice 

[in]
A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_drawindexedprimitive2">D3DDDIARG_DRAWINDEXEDPRIMITIVE2</a> structure that describes the primitive to draw.

### -param Arg3

*dwIndicesSize* [in]

The size, in bytes, of indexes in the buffer that <i>pIndexBuffer</i> points to. This size is 2 or 4 bytes.

### -param Arg4

*pIndexBuffer* [in]

A pointer to a buffer of index data to be drawn.

### -param Arg5

*pFlagBuffer* [in, optional]

A pointer to a 32-bit value that contains triangle-edge flags, which are used only during line-fill mode. The first three bits (0/1/2) of the 32-bit value specify how the three edges of the corresponding triangle are rendered. If a bit is set to 1, its associated triangle edge is rendered; otherwise, the edge is not rendered.

If the pointer is <b>NULL</b>, the user-mode display driver should use its fast path to draw primitives.

## -returns

<b>DrawIndexedPrimitive2</b> returns S_OK or an appropriate error result if the primitive is not successfully drawn.

## -remarks

Stream zero contains transform indices and is the only stream that should be accessed. 

When the Microsoft Direct3D runtime specifies triangle-edge flags in the value that the <i>pFlagBuffer</i> parameter points to, the runtime also specifies to draw only one triangle (that is, the runtime specifies the D3DPT_TRIANGLELIST value in the <b>PrimitiveType</b> member and 0x00000001 in the <b>PrimitiveCount</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_drawindexedprimitive2">D3DDDIARG_DRAWINDEXEDPRIMITIVE2</a> structure that the <i>pData</i> parameter points to).

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_drawindexedprimitive2">D3DDDIARG_DRAWINDEXEDPRIMITIVE2</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_drawindexedprimitive">DrawIndexedPrimitive</a>

