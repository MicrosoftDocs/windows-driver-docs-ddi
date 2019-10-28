---
UID: NC:d3dumddi.PFND3DDDI_SETVERTEXSHADERFUNC
title: PFND3DDDI_SETVERTEXSHADERFUNC (d3dumddi.h)
description: The SetVertexShaderFunc function sets the vertex shader code so that all of the subsequent drawing operations use that code.
old-location: display\setvertexshaderfunc.htm
tech.root: display
ms.assetid: 2cea4812-7eba-4558-9c2e-30de460be21f
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETVERTEXSHADERFUNC, PFND3DDDI_SETVERTEXSHADERFUNC callback, SetVertexShaderFunc, SetVertexShaderFunc callback function [Display Devices], UserModeDisplayDriver_Functions_aeaa5094-5619-4cf5-b2c3-c4b6aeed9b33.xml, d3dumddi/SetVertexShaderFunc, display.setvertexshaderfunc
ms.topic: callback
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
 - "d3dumddi/SetVertexShaderFunc"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetVertexShaderFunc
product:
 - Windows
---

# PFND3DDDI_SETVERTEXSHADERFUNC callback function

## -description

The <i>SetVertexShaderFunc</i> function sets the vertex shader code so that all of the subsequent drawing operations use that code.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*hShaderHandle* [in]

A handle to the vertex shader code object.

## -returns

<i>SetVertexShaderFunc</i> returns S_OK or an appropriate error result if the vertex shader code is not successfully set.

## -remarks

After setting the vertex shader code, all of the drawing operations use that code until another code is selected.

For user-mode display drivers that support vertex shaders before version 2.0, the Microsoft Direct3D runtime passes 0 in the <i>hShaderHandle</i> parameter to indicate a fixed-function pipeline. For user-mode display drivers that support vertex shader version 2.0 or later, the runtime converts Direct3D fixed-function vertex state to vertex shader version 2.0. For more information fixed-function state, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/converting-the-direct3d-fixed-function-state">Converting the Direct3D Fixed-Function State</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

