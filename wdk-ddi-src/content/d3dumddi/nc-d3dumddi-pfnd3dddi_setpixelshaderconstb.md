---
UID: NC:d3dumddi.PFND3DDDI_SETPIXELSHADERCONSTB
title: PFND3DDDI_SETPIXELSHADERCONSTB (d3dumddi.h)
description: The SetPixelShaderConstB function sets one or more pixel shader constant registers with Boolean values.
old-location: display\setpixelshaderconstb.htm
tech.root: display
ms.assetid: 6f7c8932-9332-4ff2-89ab-2f9a66783326
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETPIXELSHADERCONSTB callback function"]
ms.keywords: PFND3DDDI_SETPIXELSHADERCONSTB, PFND3DDDI_SETPIXELSHADERCONSTB callback, SetPixelShaderConstB, SetPixelShaderConstB callback function [Display Devices], UserModeDisplayDriver_Functions_1f26c07c-fd24-4b1f-bc9d-23f6b8dae95f.xml, d3dumddi/SetPixelShaderConstB, display.setpixelshaderconstb
f1_keywords:
 - "d3dumddi/SetPixelShaderConstB"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- SetPixelShaderConstB
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETPIXELSHADERCONSTB callback function


## -description


The <i>SetPixelShaderConstB</i> function sets one or more pixel shader constant registers with Boolean values. 


## -parameters




### -param hDevice 

[in] A handle to the display device (graphics context).


### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setpixelshaderconst">D3DDDIARG_SETPIXELSHADERCONST</a> structure that describes how to set the pixel shader constant registers.

### -param Arg3

*pRegisters* [in]

A pointer to a buffer that contains BOOL values to copy.


## -returns



<i>SetPixelShaderConstB</i> returns S_OK or an appropriate error result if the pixel shader constant registers are not successfully set with Boolean values.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setpixelshaderconst">D3DDDIARG_SETPIXELSHADERCONST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
 

 

