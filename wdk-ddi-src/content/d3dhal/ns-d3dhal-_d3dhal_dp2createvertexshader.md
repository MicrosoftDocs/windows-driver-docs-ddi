---
UID: NS:d3dhal._D3DHAL_DP2CREATEVERTEXSHADER
title: _D3DHAL_DP2CREATEVERTEXSHADER (d3dhal.h)
description: DirectX 8.0 and later versions only. The D3DHAL_DP2CRED3dDrawPrimitives2ATEVERTEXSHADER structure is used to create a vertex shader when a D3DDP2OP_CREATEVERTEXSHADER opcode is received by .
old-location: display\d3dhal_dp2createvertexshader.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DHAL_DP2CREATEVERTEXSHADER structure"]
ms.keywords: "*LPD3DHAL_DP2CREATEVERTEXSHADER, D3DHAL_DP2CREATEVERTEXSHADER, D3DHAL_DP2CREATEVERTEXSHADER structure [Display Devices], LPD3DHAL_DP2CREATEVERTEXSHADER, LPD3DHAL_DP2CREATEVERTEXSHADER structure pointer [Display Devices], _D3DHAL_DP2CREATEVERTEXSHADER, d3dhal/D3DHAL_DP2CREATEVERTEXSHADER, d3dhal/LPD3DHAL_DP2CREATEVERTEXSHADER, d3dstrct_540af788-1ffd-4696-ac9e-5268c379a14e.xml, display.d3dhal_dp2createvertexshader"
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
targetos: Windows
req.typenames: D3DHAL_DP2CREATEVERTEXSHADER
f1_keywords:
 - _D3DHAL_DP2CREATEVERTEXSHADER
 - d3dhal/_D3DHAL_DP2CREATEVERTEXSHADER
 - D3DHAL_DP2CREATEVERTEXSHADER
 - d3dhal/D3DHAL_DP2CREATEVERTEXSHADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - D3DHAL_DP2CREATEVERTEXSHADER
---

# _D3DHAL_DP2CREATEVERTEXSHADER structure


## -description

   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2CRE<a href="/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>ATEVERTEXSHADER structure is used to create a vertex shader when a D3DDP2OP_CREATEVERTEXSHADER opcode is received by .

## -struct-fields

### -field dwHandle

Specifies the handle to the vertex shader that is assigned by the runtime. This value is guaranteed to be subzero. Furthermore, although flexible vertex format (FVF) codes are part of the shader handle namespace, it is guaranteed that the handle passed will not be an FVF code.

### -field dwDeclSize

Specifies the shader declaration size in bytes.

### -field dwCodeSize

Specifies the shader code size in bytes.

## -remarks

Before invoking the driver, the runtime performs validation to ensure that the specified shader is legal for the specified shader language version. The runtime flushes all pending state and rendering when this token is to be sent to the driver. Thus, processing of this token is assumed to be synchronous with the runtime and the driver reports failure of the creation request by failing the <a href="/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> DDI call. Thus, the driver should validate the given shader declaration and code on receipt of this token and report success or failure accordingly. 

See <a href="/windows-hardware/drivers/ddi/index">Direct3D Driver Shader Codes</a> for information about the format of an individual shader code and the tokens that comprise each shader code.

## -see-also

D3DDP2OP_CREATEVERTEXSHADER



<a href="/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2vertexshader">D3DHAL_DP2VERTEXSHADER</a>



<a href="/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
