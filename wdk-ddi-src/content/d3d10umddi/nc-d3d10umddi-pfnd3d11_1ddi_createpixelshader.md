---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEPIXELSHADER
title: PFND3D11_1DDI_CREATEPIXELSHADER (d3d10umddi.h)
description: Converts pixel shader code into a hardware-specific format and associates this code with a shader handle.
old-location: display\createpixelshader_d3d11_1_.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_CREATEPIXELSHADER callback function"]
ms.keywords: CreatePixelShader(D3D11_1), CreatePixelShader(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CREATEPIXELSHADER, PFND3D11_1DDI_CREATEPIXELSHADER callback, d3d10umddi/CreatePixelShader(D3D11_1), display.createpixelshader_d3d11_1_, display.pfncreatepixelshader
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_CREATEPIXELSHADER
 - d3d10umddi/PFND3D11_1DDI_CREATEPIXELSHADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CreatePixelShader(D3D11_1)
product:
 - Windows
---

# PFND3D11_1DDI_CREATEPIXELSHADER callback function


## -description

Converts pixel shader code into a hardware-specific format and associates this code with a shader handle.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param pShaderCode

A pointer to an array of CONST UINT tokens that make up the shader code. The first token in the shader code stream is always the version token. The next token in the stream is the length token that determines the end of the shader code stream. For more information about the format of Direct3D version 11.1 shader code, see the comments inside the D3d10tokenizedprogramformat.hpp header file that is included with the WDK.

### -param Arg3

*hShader* [in]

A handle to the driver's private data for the pixel shader. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivateshadersize">CalcPrivateShaderSize(D3D11_1)</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader object.

### -param Arg4

*hRTShader* [in]

A handle to the pixel shader that the driver should use when it calls back into the Direct3D runtime.

### -param Arg5

*pSignatures* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_stage_io_signatures">D3D11_1DDIARG_STAGE_IO_SIGNATURES</a> structure that makes up the shader's signature.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is incorrect; therefore, the runtime will not call the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshader">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivateshadersize">CalcPrivateShaderSize(D3D11_1)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_stage_io_signatures">D3D11_1DDIARG_STAGE_IO_SIGNATURES</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshader">DestroyShader</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
