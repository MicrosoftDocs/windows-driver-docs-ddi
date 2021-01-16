---
UID: NC:d3dumddi.PFND3DDDI_CREATEVERTEXSHADERDECL
title: PFND3DDDI_CREATEVERTEXSHADERDECL (d3dumddi.h)
description: The CreateVertexShaderDecl function converts the vertex shader declaration into a hardware-specific format and associates the declaration with a shader handle.
old-location: display\createvertexshaderdecl.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_CREATEVERTEXSHADERDECL callback function"]
ms.keywords: CreateVertexShaderDecl, CreateVertexShaderDecl callback function [Display Devices], PFND3DDDI_CREATEVERTEXSHADERDECL, PFND3DDDI_CREATEVERTEXSHADERDECL callback, UserModeDisplayDriver_Functions_9b214e45-8b3c-49e9-ae72-6b7c2391c256.xml, d3dumddi/CreateVertexShaderDecl, display.createvertexshaderdecl
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
 - PFND3DDDI_CREATEVERTEXSHADERDECL
 - d3dumddi/PFND3DDDI_CREATEVERTEXSHADERDECL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_CREATEVERTEXSHADERDECL
---

# PFND3DDDI_CREATEVERTEXSHADERDECL callback function


## -description

The <b>CreateVertexShaderDecl</b> function converts the vertex shader declaration into a hardware-specific format and associates the declaration with a shader handle.

## -parameters

### -param hDevice 

[in]
A handle to the display device (graphics context).

### -param Arg2

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createvertexshaderdecl">D3DDDIARG_CREATEVERTEXSHADERDECL</a> structure that retrieves the shader handle that is associated with the vertex shader declaration that is specified by <i>pVertexElements</i>.

### -param Arg3

*pVertexElements* [in]

An array of <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddivertexelement">D3DDDIVERTEXELEMENT</a> structures that make up the vertex shader declaration.

## -returns

<b>CreateVertexShaderDecl</b> returns S_OK or an appropriate error result if the vertex shader declaration object is not successfully created.

## -remarks

The array of D3DDDIVERTEXELEMENT structures specified by <i>pVertexElements</i> defines vertex data into the pipeline. 

For more information about programming shader assemblers, see <a href="/windows-hardware/drivers/display/processing-shader-codes">Processing Shader Codes</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createvertexshaderdecl">D3DDDIARG_CREATEVERTEXSHADERDECL</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddivertexelement">D3DDDIVERTEXELEMENT</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

