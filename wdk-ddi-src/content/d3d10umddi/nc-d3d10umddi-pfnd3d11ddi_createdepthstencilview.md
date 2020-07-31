---
UID: NC:d3d10umddi.PFND3D11DDI_CREATEDEPTHSTENCILVIEW
title: PFND3D11DDI_CREATEDEPTHSTENCILVIEW (d3d10umddi.h)
description: The CreateDepthStencilView(D3D11) function creates a depth-stencil view.
old-location: display\createdepthstencilview_d3d11_.htm
ms.assetid: cf4c34da-71df-4b49-b1c8-73d1a2dbc3cb
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_CREATEDEPTHSTENCILVIEW callback function"]
ms.keywords: CreateDepthStencilView, CreateDepthStencilView callback function [Display Devices], PFND3D11DDI_CREATEDEPTHSTENCILVIEW, PFND3D11DDI_CREATEDEPTHSTENCILVIEW callback, UserModeDisplayDriverDx11_Functions_b6fd7f03-f477-4372-aac0-14740af1ca43.xml, d3d10umddi/CreateDepthStencilView, display.createdepthstencilview_d3d11_
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateDepthStencilView(D3D11) is supported beginning with the Windows 7 operating system.
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
 - "d3d10umddi/CreateDepthStencilView"
 - "CreateDepthStencilView"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CreateDepthStencilView
product:
 - Windows
---

# PFND3D11DDI_CREATEDEPTHSTENCILVIEW callback function

## -description

The <b>CreateDepthStencilView(D3D11)</b> function creates a depth-stencil view.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateDepthStencilView* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createdepthstencilview">D3D11DDIARG_CREATEDEPTHSTENCILVIEW</a> structure that describes the parameters that the user-mode display driver uses to create a depth-stencil view.

### -param Arg3

*hDepthStencilView* [in]

A handle to the driver's private data for the depth stencil view.

### -param Arg4

*hRTDepthStencilView* [in]

A handle to the shader resource view that the driver should use when it calls back into the Direct3D runtime.

## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilview">DestroyDepthStencilView</a> function to destroy the handle that the <i>hDepthStencilView</i> parameter specifies.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivatedepthstencilviewsize">CalcPrivateDepthStencilViewSize(D3D11)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createdepthstencilview">D3D11DDIARG_CREATEDEPTHSTENCILVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilview">DestroyDepthStencilView</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

