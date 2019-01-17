---
UID: NC:d3dumddi.PFND3DDDI_CREATEVERTEXSHADERFUNC
title: PFND3DDDI_CREATEVERTEXSHADERFUNC
description: The CreateVertexShaderFunc function converts vertex shader code into a hardware-specific format and associates the code with a shader handle.
old-location: display\createvertexshaderfunc.htm
tech.root: display
ms.assetid: e986d37a-6039-4bc4-b5e8-6c4d4d7adedd
ms.date: 05/10/2018
ms.keywords: CreateVertexShaderFunc, CreateVertexShaderFunc callback function [Display Devices], PFND3DDDI_CREATEVERTEXSHADERFUNC, PFND3DDDI_CREATEVERTEXSHADERFUNC callback, UserModeDisplayDriver_Functions_bb697f1f-765f-46d9-961a-f4e8060727bc.xml, d3dumddi/CreateVertexShaderFunc, display.createvertexshaderfunc
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	CreateVertexShaderFunc
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATEVERTEXSHADERFUNC callback function


## -description


The <b>CreateVertexShaderFunc</b> function converts vertex shader code into a hardware-specific format and associates the code with a shader handle.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *

*pCode* [in]

An array of CONST UINT tokens that make up the vertex shader code.

### -param *

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542973">D3DDDIARG_CREATEVERTEXSHADERFUNC</a> structure that retrieves the shader handle that is associated with the vertex shader code that is specified by <b>pCode</b>.


## -returns



<b>CreateVertexShaderFunc</b> returns S_OK or an appropriate error result if the vertex shader code object is not successfully created.




## -remarks



For more information about programming shader assemblers, see <a href="https://msdn.microsoft.com/c858766c-b414-4971-b4d9-23ec94aca8ea">Processing Shader Codes</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542973">D3DDDIARG_CREATEVERTEXSHADERFUNC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

