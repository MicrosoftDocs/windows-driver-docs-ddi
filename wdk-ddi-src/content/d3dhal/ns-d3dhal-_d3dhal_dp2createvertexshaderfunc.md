---
UID: NS:d3dhal._D3DHAL_DP2CREATEVERTEXSHADERFUNC
title: _D3DHAL_DP2CREATEVERTEXSHADERFUNC (d3dhal.h)
description: DirectX 9.0 and later versions only. The D3DHAL_DP2CREATEVERTEXSHADERFUNC structure is used to create a vertex shader code object when a D3DDP2OP_CREATEVERTEXSHADERFUNC opcode is received by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2createvertexshaderfunc.htm
tech.root: display
ms.assetid: 2b7456e5-a6fa-42bf-aace-21d555c3e821
ms.date: 05/10/2018
keywords: ["D3DHAL_DP2CREATEVERTEXSHADERFUNC structure"]
ms.keywords: "*LPD3DHAL_DP2CREATEVERTEXSHADERFUNC, D3DHAL_DP2CREATEVERTEXSHADERFUNC, D3DHAL_DP2CREATEVERTEXSHADERFUNC structure [Display Devices], LPD3DHAL_DP2CREATEVERTEXSHADERFUNC, LPD3DHAL_DP2CREATEVERTEXSHADERFUNC structure pointer [Display Devices], _D3DHAL_DP2CREATEVERTEXSHADERFUNC, d3dhal/D3DHAL_DP2CREATEVERTEXSHADERFUNC, d3dhal/LPD3DHAL_DP2CREATEVERTEXSHADERFUNC, d3dstrct_cb83183c-18cc-4e11-814f-2b50836cbe39.xml, display.d3dhal_dp2createvertexshaderfunc"
f1_keywords:
 - "d3dhal/D3DHAL_DP2CREATEVERTEXSHADERFUNC"
 - "D3DHAL_DP2CREATEVERTEXSHADERFUNC"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- D3DHAL_DP2CREATEVERTEXSHADERFUNC
targetos: Windows
req.typenames: D3DHAL_DP2CREATEVERTEXSHADERFUNC
---

# _D3DHAL_DP2CREATEVERTEXSHADERFUNC structure


## -description



   DirectX 9.0 and later versions only.
   

The D3DHAL_DP2CREATEVERTEXSHADERFUNC structure is used to create a vertex shader code object when a D3DDP2OP_CREATEVERTEXSHADERFUNC opcode is received by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>.


## -struct-fields




### -field dwHandle

Specifies the handle to the vertex shader code that is assigned by the runtime. This value is guaranteed to be subzero.


### -field dwSize

Specifies the shader code size in bytes.


## -remarks



When the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> function with this token, the driver should validate the given shader code and report success or failure accordingly. 

Vertex shader code follows D3DHAL_DP2CREATEVERTEXSHADERFUNC in the command stream. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Direct3D Driver Shader Codes</a> for information about the format of individual shader code and the tokens that comprise each shader code. 

The DirectX 9.0 runtime sets <b>dwHandle</b> to zero to indicate a fixed function pipeline.




## -see-also




D3DDP2OP_CREATEVERTEXSHADERFUNC



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2createvertexshaderdecl">D3DHAL_DP2CREATEVERTEXSHADERDECL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2vertexshader">D3DHAL_DP2VERTEXSHADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

