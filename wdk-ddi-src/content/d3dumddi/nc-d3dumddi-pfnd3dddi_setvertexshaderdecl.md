---
UID: NC:d3dumddi.PFND3DDDI_SETVERTEXSHADERDECL
title: PFND3DDDI_SETVERTEXSHADERDECL (d3dumddi.h)
description: The SetVertexShaderDecl function sets the vertex shader declaration so that all of the subsequent drawing operations use that declaration.
old-location: display\setvertexshaderdecl.htm
tech.root: display
ms.assetid: 6387d632-78e2-4594-a58a-b11b2e831cc0
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETVERTEXSHADERDECL, PFND3DDDI_SETVERTEXSHADERDECL callback, SetVertexShaderDecl, SetVertexShaderDecl callback function [Display Devices], UserModeDisplayDriver_Functions_83e6bdef-65e0-4357-aa4c-51e20cbeb6d5.xml, d3dumddi/SetVertexShaderDecl, display.setvertexshaderdecl
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
 - "d3dumddi/SetVertexShaderDecl"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetVertexShaderDecl
product:
 - Windows
---

# PFND3DDDI_SETVERTEXSHADERDECL callback function

## -description

The <i>SetVertexShaderDecl</i> function sets the vertex shader declaration so that all of the subsequent drawing operations use that declaration.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*hShaderHandle* [in]

A handle to the vertex shader declaration object.

## -returns

<i>SetVertexShaderDecl</i> returns S_OK or an appropriate error result if the vertex shader declaration is not successfully set.

## -remarks

After setting the vertex shader declaration, all of the drawing operations use that declaration until another declaration is selected.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

