---
UID: NC:d3d10umddi.PFND3D10DDI_SETSHADER
title: PFND3D10DDI_SETSHADER (d3d10umddi.h)
description: The CsSetShader function sets the compute shader code so that all of the subsequent dispatching operations use that code.
old-location: display\cssetshader.htm
ms.assetid: ab689c60-3099-4d69-a7e2-5edfb623cbc3
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_SETSHADER callback function"]
ms.keywords: CsSetShader, CsSetShader callback function [Display Devices], PFND3D10DDI_SETSHADER, PFND3D10DDI_SETSHADER callback, UserModeDisplayDriverDx11_Functions_4e96f922-1a22-45c3-9c50-a4b71a79f695.xml, d3d10umddi/CsSetShader, display.cssetshader
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CsSetShader is supported beginning with the Windows 7 operating system.
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
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D10DDI_SETSHADER
 - d3d10umddi/PFND3D10DDI_SETSHADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CsSetShader
product:
 - Windows
---

# PFND3D10DDI_SETSHADER callback function


## -description

The <b>CsSetShader</b> function sets the compute shader code so that all of the subsequent dispatching operations use that code.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hShader* [in]

A handle to the compute shader code object.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of<b>CsSetShader</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

The <b>DsSetShader</b> function sets the domain shader code so that all of the subsequent drawing operations use that code. 

The <b>VsSetShader</b> function sets the vertex shader code so that all of the subsequent drawing operations use that code. 

The <b>GsSetShader</b> function sets the geometry shader code so that all of the subsequent drawing operations use that code.

The <b>HsSetShader</b> function sets the hull shader code so that all of the subsequent drawing operations use that code. 

The <b>PsSetShader</b> function sets a pixel shader to be used in all drawing operations.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>