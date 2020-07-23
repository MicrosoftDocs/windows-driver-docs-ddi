---
UID: NS:d3dumddi._D3DDDIARG_CREATEPIXELSHADER
title: _D3DDDIARG_CREATEPIXELSHADER (d3dumddi.h)
description: The D3DDDIARG_CREATEPIXELSHADER structure specifies a shader handle to associate with pixel shader code.
old-location: display\d3dddiarg_createpixelshader.htm
tech.root: display
ms.assetid: dc7baff1-7e74-4666-805b-33b524c89c1d
ms.date: 05/10/2018
keywords: ["_D3DDDIARG_CREATEPIXELSHADER structure"]
ms.keywords: D3DDDIARG_CREATEPIXELSHADER, D3DDDIARG_CREATEPIXELSHADER structure [Display Devices], UMDisplayDriver_param_Structs_c1c78eaf-3eb9-4518-9b3c-f3fd5d6ce1f7.xml, _D3DDDIARG_CREATEPIXELSHADER, d3dumddi/D3DDDIARG_CREATEPIXELSHADER, display.d3dddiarg_createpixelshader
f1_keywords:
 - "d3dumddi/D3DDDIARG_CREATEPIXELSHADER"
 - "D3DDDIARG_CREATEPIXELSHADER"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_CREATEPIXELSHADER
targetos: Windows
req.typenames: D3DDDIARG_CREATEPIXELSHADER
---

# _D3DDDIARG_CREATEPIXELSHADER structure


## -description


The D3DDDIARG_CREATEPIXELSHADER structure specifies a shader handle to associate with pixel shader code.


## -struct-fields




### -field CodeSize

[in] The size, in bytes, of the pixel shader code that is passed in the <i>pCode</i> parameter in a call to the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createpixelshader">CreatePixelShader</a> function.


### -field ShaderHandle

[out] A handle to the pixel shader code.


## -remarks



For more information about programming shader assemblers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/processing-shader-codes">Processing Shader Codes</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createpixelshader">CreatePixelShader</a>
 

 

