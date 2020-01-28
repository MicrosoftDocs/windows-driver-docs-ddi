---
UID: NC:d3dumddi.PFND3DDDI_DELETEVERTEXSHADERFUNC
title: PFND3DDDI_DELETEVERTEXSHADERFUNC (d3dumddi.h)
description: The DeleteVertexShaderFunc function cleans up driver-side resources that are associated with vertex shader code.
old-location: display\deletevertexshaderfunc.htm
tech.root: display
ms.assetid: 780fc47c-bbb9-400a-a2f3-cdce4a18072f
ms.date: 05/10/2018
ms.keywords: DeleteVertexShaderFunc, DeleteVertexShaderFunc callback function [Display Devices], PFND3DDDI_DELETEVERTEXSHADERFUNC, PFND3DDDI_DELETEVERTEXSHADERFUNC callback, UserModeDisplayDriver_Functions_fda8f115-6f28-4295-b74e-14f32168a616.xml, d3dumddi/DeleteVertexShaderFunc, display.deletevertexshaderfunc
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
 - "d3dumddi/DeleteVertexShaderFunc"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - DeleteVertexShaderFunc
product:
 - Windows
---

# PFND3DDDI_DELETEVERTEXSHADERFUNC callback function

## -description

The <b>DeleteVertexShaderFunc</b> function cleans up driver-side resources that are associated with vertex shader code.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*hShaderHandle* [in]

A handle to the vertex shader code object.

## -returns

<b>DeleteVertexShaderFunc</b> returns S_OK or an appropriate error result if the vertex shader code object is not successfully cleaned up.

## -remarks

The <b>DeleteVertexShaderFunc</b> function notifies the driver about the deletion of the vertex shader code object that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createvertexshaderfunc">CreateVertexShaderFunc</a> function created. The driver can then clean up any driver-side resources that are associated with the vertex shader code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createvertexshaderfunc">CreateVertexShaderFunc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

