---
UID: NC:d3dumddi.PFND3DDDI_DELETEPIXELSHADER
title: PFND3DDDI_DELETEPIXELSHADER (d3dumddi.h)
description: The DeletePixelShader function cleans up driver-side resources that are associated with pixel shader code.
old-location: display\deletepixelshader.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DELETEPIXELSHADER callback function"]
ms.keywords: DeletePixelShader, DeletePixelShader callback function [Display Devices], PFND3DDDI_DELETEPIXELSHADER, PFND3DDDI_DELETEPIXELSHADER callback, UserModeDisplayDriver_Functions_2994cbd5-2661-40e3-bdcd-3b2bfc209c24.xml, d3dumddi/DeletePixelShader, display.deletepixelshader
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
 - PFND3DDDI_DELETEPIXELSHADER
 - d3dumddi/PFND3DDDI_DELETEPIXELSHADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_DELETEPIXELSHADER
product:
 - Windows
---

# PFND3DDDI_DELETEPIXELSHADER callback function


## -description

The <b>DeletePixelShader</b> function cleans up driver-side resources that are associated with pixel shader code.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*hShaderHandle* [in]

A handle to the pixel shader code object.

## -returns

<b>DeletePixelShader</b> returns S_OK or an appropriate error result if the pixel shader code object is not successfully cleaned up.

## -remarks

The <b>DeletePixelShader</b> function notifies the driver about the deletion of the pixel shader code object that the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createpixelshader">CreatePixelShader</a> function created. The driver can then clean up any driver-side resources that are associated with the pixel shader code.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createpixelshader">CreatePixelShader</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

