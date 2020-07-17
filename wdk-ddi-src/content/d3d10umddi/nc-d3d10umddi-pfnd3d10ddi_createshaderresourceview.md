---
UID: NC:d3d10umddi.PFND3D10DDI_CREATESHADERRESOURCEVIEW
title: PFND3D10DDI_CREATESHADERRESOURCEVIEW (d3d10umddi.h)
description: The CreateShaderResourceView function creates a shader resource view.
old-location: display\createshaderresourceview.htm
ms.assetid: 3b1c998d-3fde-4712-ba74-7c8033033182
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CREATESHADERRESOURCEVIEW callback function"]
ms.keywords: CreateShaderResourceView, CreateShaderResourceView callback function [Display Devices], PFND3D10DDI_CREATESHADERRESOURCEVIEW, PFND3D10DDI_CREATESHADERRESOURCEVIEW callback, UserModeDisplayDriverDx10_Functions_183935f7-c6ab-4ea9-9e33-a4586daf3097.xml, d3d10umddi/CreateShaderResourceView, display.createshaderresourceview
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/CreateShaderResourceView"
 - "CreateShaderResourceView"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CreateShaderResourceView
product:
 - Windows
---

# PFND3D10DDI_CREATESHADERRESOURCEVIEW callback function

## -description

The <b>CreateShaderResourceView</b> function creates a shader resource view.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateShaderResourceView* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createshaderresourceview">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a> structure that describes the parameters that the user-mode display driver uses to create a shader resource view.

### -param Arg3

*hShaderResourceView* [in]

A handle to the driver's private data for the shader resource view.

### -param Arg4

*hRTShaderResourceView* [in]

A handle to the shader resource view that the driver should use anytime it calls back into the Direct3D runtime.

## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshaderresourceview">DestroyShaderResourceView</a> function to destroy the handle that the <i>hShaderResourceView</i> parameter specifies.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize">CalcPrivateShaderResourceViewSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createshaderresourceview">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyshaderresourceview">DestroyShaderResourceView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

