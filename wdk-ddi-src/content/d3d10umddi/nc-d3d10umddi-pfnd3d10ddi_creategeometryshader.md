---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEGEOMETRYSHADER
title: PFND3D10DDI_CREATEGEOMETRYSHADER
author: windows-driver-content
description: The CreateGeometryShader function creates a geometry shader.
old-location: display\creategeometryshader.htm
ms.assetid: b3b422e3-f8da-4aad-a230-7c7e26dd72ec
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CreateGeometryShader, CreateGeometryShader callback function [Display Devices], PFND3D10DDI_CREATEGEOMETRYSHADER, PFND3D10DDI_CREATEGEOMETRYSHADER callback, UserModeDisplayDriverDx10_Functions_9802537e-bb60-4aae-8049-11ccff9f99a5.xml, d3d10umddi/CreateGeometryShader, display.creategeometryshader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CreateGeometryShader
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_CREATEGEOMETRYSHADER callback function


## -description


The <b>CreateGeometryShader</b> function creates a geometry shader.


## -parameters




### -param Arg1


### -param *pShaderCode


### -param Arg2


### -param Arg3


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hRTShader [in]

 A handle to the geometry shader that the driver should use anytime it calls back into the Direct3D runtime. 


#### - hShader [in]

 A handle to the driver's private data for the geometry shader. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/76cdddb0-b927-4547-ae1d-f5105905633b">CalcPrivateShaderSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader object. 


#### - pCode [in]

 An array of CONST UINT tokens that make up the shader code. The first token in the shader code stream is always the version token. The next token in the stream is the length token that determines the end of the shader code stream. For more information about the format of Direct3D version 10 shader code, see the comments inside the <i>D3d10tokenizedprogramformat.hpp</i> header file that is included with the WDK. 


#### - pSignatures [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541746">D3D10DDIARG_STAGE_IO_SIGNATURES</a> structure that makes up the shader's signature.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.




## -see-also




<a href="https://msdn.microsoft.com/76cdddb0-b927-4547-ae1d-f5105905633b">CalcPrivateShaderSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541746">D3D10DDIARG_STAGE_IO_SIGNATURES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

