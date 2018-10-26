---
UID: NS:d3dhal._D3DHAL_DP2VERTEXSHADER
title: "_D3DHAL_DP2VERTEXSHADER"
author: windows-driver-content
description: DirectX 8.0 and later versions only. The D3DHAL_DP2VERTEXSHADER structure sets the current vertex shader, or deletes a vertex shader, depending on the opcode received (D3DDP2OP_SETVERTEXSHADER or D3DDP2OP_DELETEVERTEXSHADER) by D3dDrawPrimitives2.
old-location: display\d3dhal_dp2vertexshader.htm
tech.root: display
ms.assetid: 9207768b-530a-49d5-999e-0e8eb6bd1fe5
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2VERTEXSHADER, D3DHAL_DP2VERTEXSHADER, D3DHAL_DP2VERTEXSHADER structure [Display Devices], LPD3DHAL_DP2VERTEXSHADER, LPD3DHAL_DP2VERTEXSHADER structure pointer [Display Devices], _D3DHAL_DP2VERTEXSHADER, d3dhal/D3DHAL_DP2VERTEXSHADER, d3dhal/LPD3DHAL_DP2VERTEXSHADER, d3dstrct_84401bfa-f79d-4128-9989-1223284f25b0.xml, display.d3dhal_dp2vertexshader"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_DP2VERTEXSHADER
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2VERTEXSHADER
---

# _D3DHAL_DP2VERTEXSHADER structure


## -description



   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2VERTEXSHADER structure sets the current vertex shader, or deletes a vertex shader, depending on the opcode received (D3DDP2OP_SETVERTEXSHADER or D3DDP2OP_DELETEVERTEXSHADER) by <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>.


## -struct-fields




### -field dwHandle

A handle to the display.


## -remarks



All DirectX 8.0 level drivers must support the D3DDP2OP_SETVERTEXSHADER token because it is sent even if the driver does not support programmable vertex processing. In that case, however, the shader handle is always an FVF code indicating fixed function processing of the vertex data. The driver should use the FVF code stored in the <b>dwHandle</b> member as the format of the vertex data in stream zero. A driver that does support programmable vertex processing must examine the handle to determine whether it refers to a shader previously created with D3DDP2OP_CREATEVERTEXSHADER or an FVF code and take the appropriate action.

Pixel and vertex shaders are orthogonal. Thus, if a legacy FVF code is selected as the current vertex shader this does not imply legacy pixel processing. In order to reset pixel processing to a subprogrammable mode the current pixel shader must also be set to zero. Care should be taken in the driver to only reset vertex processing state to a fixed function mode and not pixel processing state when the vertex shader is set to an FVF code.

When switching from fixed function vertex processing to programmable vertex processing, the values of legacy render state and matrices should be preserved. If and when a switch from programmable to fixed function vertex processing occurs (the driver receives a D3DDP2OP_SETVERTEXSHADER with an FVF as the shader handle), that preserved state should be restored.

When switching between programmable shaders, any constant register that has a value specified in the definition of that shader should be set to that value. The values of all other constant registers should remain unchanged.

For D3DDP2OP_SETVERTEXSHADERDECL operations, the runtime specifies a legacy FVF code or a DirectX 9.0 declaration handle in the <b>dwHandle</b> member. The runtime indicates a DirectX 9.0 declaration handle by setting bit 0 of the handle. For D3DDP2OP_SETVERTEXSHADERFUNC operations, the runtime sets <b>dwHandle</b> to zero to indicate a fixed function pipeline.




## -see-also




D3DDP2OP_CREATEVERTEXSHADER



D3DDP2OP_DELETEVERTEXSHADER



D3DDP2OP_DELETEVERTEXSHADERDECL



D3DDP2OP_DELETEVERTEXSHADERFUNC



D3DDP2OP_SETSTREAMSOURCE



D3DDP2OP_SETSTREAMSOURCEUM



D3DDP2OP_SETVERTEXSHADER



D3DDP2OP_SETVERTEXSHADERDECL



D3DDP2OP_SETVERTEXSHADERFUNC



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545478">D3DHAL_DP2CREATEVERTEXSHADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545826">D3DHAL_DP2SETVERTEXSHADERCONST</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>
 

 

