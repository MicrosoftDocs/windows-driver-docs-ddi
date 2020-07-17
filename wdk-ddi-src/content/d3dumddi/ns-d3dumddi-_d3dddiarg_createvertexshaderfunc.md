---
UID: NS:d3dumddi._D3DDDIARG_CREATEVERTEXSHADERFUNC
title: _D3DDDIARG_CREATEVERTEXSHADERFUNC (d3dumddi.h)
description: The D3DDDIARG_CREATEVERTEXSHADERFUNC structure specifies a shader handle to associate with vertex shader code.
old-location: display\d3dddiarg_createvertexshaderfunc.htm
tech.root: display
ms.assetid: 2517b7a9-76f5-46f6-9225-18081cd1d357
ms.date: 05/10/2018
keywords: ["_D3DDDIARG_CREATEVERTEXSHADERFUNC structure"]
ms.keywords: D3DDDIARG_CREATEVERTEXSHADERFUNC, D3DDDIARG_CREATEVERTEXSHADERFUNC structure [Display Devices], UMDisplayDriver_param_Structs_cbcea02a-d591-4226-8896-f8392c4b67de.xml, _D3DDDIARG_CREATEVERTEXSHADERFUNC, d3dumddi/D3DDDIARG_CREATEVERTEXSHADERFUNC, display.d3dddiarg_createvertexshaderfunc
f1_keywords:
 - "d3dumddi/D3DDDIARG_CREATEVERTEXSHADERFUNC"
 - "D3DDDIARG_CREATEVERTEXSHADERFUNC"
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
- D3DDDIARG_CREATEVERTEXSHADERFUNC
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATEVERTEXSHADERFUNC
---

# _D3DDDIARG_CREATEVERTEXSHADERFUNC structure


## -description


The D3DDDIARG_CREATEVERTEXSHADERFUNC structure specifies a shader handle to associate with vertex shader code.


## -struct-fields




### -field Size

[in] The size, in bytes, of the vertex shader code that is passed to the <i>pCode</i> parameter in a call to the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createvertexshaderfunc">CreateVertexShaderFunc</a> function.


### -field ShaderHandle

[out] A handle to the vertex shader code.


## -remarks



For more information about programming shader assemblers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/processing-shader-codes">Processing Shader Codes</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createvertexshaderfunc">CreateVertexShaderFunc</a>
 

 

