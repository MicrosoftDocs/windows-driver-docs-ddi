---
UID: NC:d3d10umddi.PFND3D11DDI_CREATEHULLSHADER
title: PFND3D11DDI_CREATEHULLSHADER
author: windows-driver-content
description: The CreateHullShader function creates a hull shader.
old-location: display\createhullshader.htm
ms.assetid: 7fe647cf-37b0-427e-9e16-664bdd365ea6
ms.date: 5/10/2018
ms.keywords: CreateHullShader, CreateHullShader callback function [Display Devices], PFND3D11DDI_CREATEHULLSHADER, PFND3D11DDI_CREATEHULLSHADER callback, UserModeDisplayDriverDx11_Functions_23b1e1ad-9451-4605-a04a-29dffc006bea.xml, d3d10umddi/CreateHullShader, display.createhullshader
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateHullShader is supported beginning with the Windows 7 operating system.
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CreateHullShader
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_CREATEHULLSHADER callback function


## -description


The <b>CreateHullShader </b> function creates a hull shader.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *pShaderCode

pCode [in]

An array of CONST UINT tokens that form the shader code. The first token in the shader code stream is always the version token. The next token in the stream is the length token that determines the end of the shader code stream. For more information about the format of Direct3D version 11 shader code, see the comments inside the <i>D3d11tokenizedprogramformat.hpp</i> header file that is included with the WDK. 

### -param Arg2

*hShader* [in]

A handle to the driver's private data for the hull shader. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/604d7475-4696-429e-a645-781931509bb6">CalcPrivateTessellationShaderSize</a>  function. The handle is just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its tessellation-shader object. 

### -param Arg3

*hRTShader* [in]

A handle to the hull shader that the driver should use when it calls back into the Direct3D runtime. 

### -param *

*pSignatures* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542105">D3D11DDIARG_TESSELLATION_IO_SIGNATURES</a> structure that forms the tessellation-shader's signature.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device is removed) in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.




## -see-also




<a href="https://msdn.microsoft.com/604d7475-4696-429e-a645-781931509bb6">CalcPrivateTessellationShaderSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542105">D3D11DDIARG_TESSELLATION_IO_SIGNATURES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

