---
UID: NS:d3dhal._D3DHAL_DP2CREATEVERTEXSHADERDECL
title: _D3DHAL_DP2CREATEVERTEXSHADERDECL (d3dhal.h)
description: DirectX 9.0 and later versions only. The D3DHAL_DP2CREATEVERTEXSHADERDECL structure is used to create a vertex shader declaration when a D3DDP2OP_CREATEVERTEXSHADERDECL opcode is received by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2createvertexshaderdecl.htm
tech.root: display
ms.assetid: 063e72ef-7d57-484a-98f8-b6166a238096
ms.date: 05/10/2018
keywords: ["_D3DHAL_DP2CREATEVERTEXSHADERDECL structure"]
ms.keywords: "*LPD3DHAL_DP2CREATEVERTEXSHADERDECL, D3DHAL_DP2CREATEVERTEXSHADERDECL, D3DHAL_DP2CREATEVERTEXSHADERDECL structure [Display Devices], LPD3DHAL_DP2CREATEVERTEXSHADERDECL, LPD3DHAL_DP2CREATEVERTEXSHADERDECL structure pointer [Display Devices], _D3DHAL_DP2CREATEVERTEXSHADERDECL, d3dhal/D3DHAL_DP2CREATEVERTEXSHADERDECL, d3dhal/LPD3DHAL_DP2CREATEVERTEXSHADERDECL, d3dstrct_ae2ef7ce-67b3-4c91-b4d8-e3ff8b82734b.xml, display.d3dhal_dp2createvertexshaderdecl"
f1_keywords:
 - "d3dhal/D3DHAL_DP2CREATEVERTEXSHADERDECL"
 - "D3DHAL_DP2CREATEVERTEXSHADERDECL"
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
- D3DHAL_DP2CREATEVERTEXSHADERDECL
targetos: Windows
req.typenames: D3DHAL_DP2CREATEVERTEXSHADERDECL
---

# _D3DHAL_DP2CREATEVERTEXSHADERDECL structure


## -description



   DirectX 9.0 and later versions only.
   

The D3DHAL_DP2CREATEVERTEXSHADERDECL structure is used to create a vertex shader declaration when a D3DDP2OP_CREATEVERTEXSHADERDECL opcode is received by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>.


## -struct-fields




### -field dwHandle

Specifies the handle to the vertex shader declaration that is assigned by the runtime. This value is guaranteed to be subzero. Flexible vertex format (FVF) codes are part of the shader declaration handle namespace. If bit zero of the handle is set, the handle passed is a shader declaration handle; otherwise, an FVF code. 


### -field dwNumVertexElements

Specifies the number of vertex elements that make up the shader declaration. 


## -remarks



When the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> function with this token, the driver should validate the given shader declaration and report success or failure accordingly. 

An array of D3DVERTEXELEMENT9 structures that define the vertex elements that make up the shader declaration follow D3DHAL_DP2CREATEVERTEXSHADERDECL in the command stream. For more information about D3DVERTEXELEMENT9, see the latest DirectX SDK documentation.

The DirectX 9.0 runtime specifies a legacy FVF code or a declaration handle in the <b>dwHandle</b> member. The runtime indicates a declaration handle by setting bit 0 of the handle. 




## -see-also




D3DDP2OP_CREATEVERTEXSHADERDECL



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2vertexshader">D3DHAL_DP2VERTEXSHADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

