---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEDOMAINSHADER
title: PFND3D11_1DDI_CREATEDOMAINSHADER
author: windows-driver-content
description: Creates a domain shader.
old-location: display\createdomainshader_d3d11_1_.htm
ms.assetid: 74e6457f-4a99-4b19-9a7e-3ebac5aef48e
ms.date: 05/10/2018
ms.keywords: CreateDomainShader(D3D11_1), CreateDomainShader(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CREATEDOMAINSHADER, PFND3D11_1DDI_CREATEDOMAINSHADER callback, d3d10umddi/CreateDomainShader(D3D11_1), display.createdomainshader_d3d11_1_, display.pfncreatedomainshader
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	CreateDomainShader(D3D11_1)
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CREATEDOMAINSHADER callback function


## -description


Creates a domain shader.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *pShaderCode 

[in] A pointer to an array of CONST UINT tokens that form the shader code. The first token in the shader code stream is always the version token. The next token in the stream is the length token that determines the end of the shader code stream. For more information about the format of Direct3D version 11 shader code, see the comments inside the D3d11tokenizedprogramformat.hpp header file that is included with the WDK. 


### -param Arg2

*hShader* [in]

A handle to the driver's private data for the domain shader. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/606b50c0-4070-4694-9299-f20e28743958">CalcPrivateTessellationShaderSize(D3D11_1)</a>  function. The handle is  just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its tessellation-shader object. 

### -param Arg3

*hRTShader* [in]

A handle to the domain shader that the driver should use when it calls back into the Direct3D runtime. 

### -param *

*pSignatures* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406326">D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES</a> structure that forms the tessellation-shader's signature.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/606b50c0-4070-4694-9299-f20e28743958">CalcPrivateTessellationShaderSize(D3D11_1)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406326">D3D11_1DDIARG_TESSELLATION_IO_SIGNATURES</a>
 

 

