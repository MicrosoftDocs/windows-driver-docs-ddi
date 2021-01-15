---
UID: NC:d3d10umddi.PFND3D11DDI_CREATESHADERRESOURCEVIEW
title: PFND3D11DDI_CREATESHADERRESOURCEVIEW (d3d10umddi.h)
description: The CreateShaderResourceView(D3D11) function creates a shader resource view.
old-location: display\createshaderresourceview_d3d11_.htm
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_CREATESHADERRESOURCEVIEW callback function"]
ms.keywords: CreateShaderResourceView, CreateShaderResourceView callback function [Display Devices], PFND3D11DDI_CREATESHADERRESOURCEVIEW, PFND3D11DDI_CREATESHADERRESOURCEVIEW callback, UserModeDisplayDriverDx11_Functions_abe7b0fb-121d-4486-af02-885ff37a4e81.xml, d3d10umddi/CreateShaderResourceView, display.createshaderresourceview_d3d11_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateShaderResourceView(D3D11) is supported beginning with the Windows 7 operating system.
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
 - PFND3D11DDI_CREATESHADERRESOURCEVIEW
 - d3d10umddi/PFND3D11DDI_CREATESHADERRESOURCEVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D11DDI_CREATESHADERRESOURCEVIEW
product:
 - Windows
---

# PFND3D11DDI_CREATESHADERRESOURCEVIEW callback function


## -description

The <b>CreateShaderResourceView(D3D11)</b> function creates a shader resource view.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateShaderResourceView* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createshaderresourceview">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a> structure that describes the parameters that the user-mode display driver uses to create a shader resource view.

### -param Arg3

*hShaderResourceView* [in]

A handle to the driver's private data for the hull shader.

### -param Arg4

*hRTShaderResourceView* [in]

A handle to the shader resource view that the driver should use when it calls back into the Direct3D runtime.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshaderresourceview">DestroyShaderResourceView</a> function to destroy the handle that the <i>hShaderResourceView</i> parameter specifies.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivateshaderresourceviewsize">CalcPrivateShaderResourceViewSize(D3D11)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createshaderresourceview">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshaderresourceview">DestroyShaderResourceView</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

