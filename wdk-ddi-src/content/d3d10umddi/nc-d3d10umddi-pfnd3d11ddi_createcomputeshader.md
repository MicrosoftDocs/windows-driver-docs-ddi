---
UID: NC:d3d10umddi.PFND3D11DDI_CREATECOMPUTESHADER
title: PFND3D11DDI_CREATECOMPUTESHADER (d3d10umddi.h)
description: The CreateComputeShader function creates a compute shader.
old-location: display\createcomputeshader.htm
ms.assetid: e62ad086-f652-4e2c-bc2d-f1ccb197f01e
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_CREATECOMPUTESHADER callback function"]
ms.keywords: CreateComputeShader, CreateComputeShader callback function [Display Devices], PFND3D11DDI_CREATECOMPUTESHADER, PFND3D11DDI_CREATECOMPUTESHADER callback, UserModeDisplayDriverDx11_Functions_37f002b7-445e-4a89-8c3d-586c8072773d.xml, d3d10umddi/CreateComputeShader, display.createcomputeshader
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateComputeShader is supported beginning with the Windows 7 operating system.
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
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11DDI_CREATECOMPUTESHADER
 - d3d10umddi/PFND3D11DDI_CREATECOMPUTESHADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CreateComputeShader
product:
 - Windows
---

# PFND3D11DDI_CREATECOMPUTESHADER callback function


## -description

The <b>CreateComputeShader</b>  function creates a compute shader.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param pShaderCode

An array of CONST UINT tokens that form the shader code. The first token in the shader code stream is always the version token. The next token in the stream is the length token that determines the end of the shader code stream. For more information about the format of Direct3D version 11 shader code, see the comments inside the <i>D3d11tokenizedprogramformat.hpp</i> header file that is included with the WDK.

### -param Arg3

*hShader* [in]

A handle to the driver's private data for the compute shader. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize">CalcPrivateShaderSize</a> function. The handle is  just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader object.

### -param Arg4

*hRTShader* [in]

A handle to the compute shader that the driver should use, when it calls back into the Direct3D runtime.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device is removed) in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshader">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize">CalcPrivateShaderSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshader">DestroyShader</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>