---
UID: NC:d3dumddi.PFND3DDDI_SETPIXELSHADERCONST
title: PFND3DDDI_SETPIXELSHADERCONST (d3dumddi.h)
description: The SetPixelShaderConst function sets one or more pixel shader constant registers with floating-point values.
old-location: display\setpixelshaderconst.htm
tech.root: display
ms.assetid: 02710936-28df-4c8f-aa1e-bdff01155608
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETPIXELSHADERCONST callback function"]
ms.keywords: PFND3DDDI_SETPIXELSHADERCONST, PFND3DDDI_SETPIXELSHADERCONST callback, SetPixelShaderConst, SetPixelShaderConst callback function [Display Devices], UserModeDisplayDriver_Functions_be972851-58a6-4f22-aae2-7948679b8bb7.xml, d3dumddi/SetPixelShaderConst, display.setpixelshaderconst
f1_keywords:
 - "d3dumddi/SetPixelShaderConst"
 - "SetPixelShaderConst"
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
- SetPixelShaderConst
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETPIXELSHADERCONST callback function


## -description


The <i>SetPixelShaderConst</i> function sets one or more pixel shader constant registers with floating-point values. 


## -parameters




### -param hDevice 
[in]
A handle to the display device (graphics context).


### -param Arg2


*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setpixelshaderconst">D3DDDIARG_SETPIXELSHADERCONST</a> structure that describes how to set the pixel shader constant registers.

### -param Arg3

*pRegisters* [in]

A pointer to a buffer that contains 4-float vectors to copy.


## -returns



<i>SetPixelShaderConst</i> returns S_OK or an appropriate error result if the pixel shader constant registers are not successfully set with floating-point values.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setpixelshaderconst">D3DDDIARG_SETPIXELSHADERCONST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
 

 

