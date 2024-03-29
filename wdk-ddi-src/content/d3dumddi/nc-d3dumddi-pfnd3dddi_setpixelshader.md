---
UID: NC:d3dumddi.PFND3DDDI_SETPIXELSHADER
title: PFND3DDDI_SETPIXELSHADER (d3dumddi.h)
description: The SetPixelShader function sets a pixel shader to be used in all drawing operations.
old-location: display\setpixelshader.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETPIXELSHADER callback function"]
ms.keywords: PFND3DDDI_SETPIXELSHADER, PFND3DDDI_SETPIXELSHADER callback, SetPixelShader, SetPixelShader callback function [Display Devices], UserModeDisplayDriver_Functions_dd7fa75c-0753-4786-b04a-2fdd0d0e7071.xml, d3dumddi/SetPixelShader, display.setpixelshader
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
 - PFND3DDDI_SETPIXELSHADER
 - d3dumddi/PFND3DDDI_SETPIXELSHADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_SETPIXELSHADER
---

# PFND3DDDI_SETPIXELSHADER callback function


## -description

The <i>SetPixelShader</i> function sets a pixel shader to be used in all drawing operations.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param unnamedParam2

*hShaderHandle* [in]

A handle to the pixel shader code object.

## -returns

<i>SetPixelShader</i> returns S_OK or an appropriate error result if the pixel shader is not successfully set.

## -remarks

All subsequent drawing operations use the given shader until another is selected.

For user-mode display drivers that support pixel shaders before version 2.0, the Microsoft Direct3D runtime passes 0 in the <i>hShaderHandle</i> parameter to indicate a fixed-function pipeline. For user-mode display drivers that support pixel shader version 2.0 or later, the runtime converts Direct3D fixed-function pixel state to pixel shader version 2.0. For more information about fixed-function state, see <a href="/windows-hardware/drivers/display/converting-the-direct3d-fixed-function-state">Converting the Direct3D Fixed-Function State</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

