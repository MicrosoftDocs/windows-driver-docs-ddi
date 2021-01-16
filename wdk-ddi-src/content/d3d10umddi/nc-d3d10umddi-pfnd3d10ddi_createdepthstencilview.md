---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEDEPTHSTENCILVIEW
title: PFND3D10DDI_CREATEDEPTHSTENCILVIEW (d3d10umddi.h)
description: The CreateDepthStencilView function creates a depth stencil view.
old-location: display\createdepthstencilview.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CREATEDEPTHSTENCILVIEW callback function"]
ms.keywords: CreateDepthStencilView, CreateDepthStencilView callback function [Display Devices], PFND3D10DDI_CREATEDEPTHSTENCILVIEW, PFND3D10DDI_CREATEDEPTHSTENCILVIEW callback, UserModeDisplayDriverDx10_Functions_299a6bcd-ba94-4568-a4fc-d89c84742c45.xml, d3d10umddi/CreateDepthStencilView, display.createdepthstencilview
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
 - PFND3D10DDI_CREATEDEPTHSTENCILVIEW
 - d3d10umddi/PFND3D10DDI_CREATEDEPTHSTENCILVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_CREATEDEPTHSTENCILVIEW
product:
 - Windows
---

# PFND3D10DDI_CREATEDEPTHSTENCILVIEW callback function


## -description

The <b>CreateDepthStencilView</b> function creates a depth stencil view.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateDepthStencilView* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdepthstencilview">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a> structure that describes the parameters that the user-mode display driver uses to create a depth stencil view.

### -param Arg3

*hDepthStencilView* [in]

A handle to the driver's private data for the depth stencil view.

### -param Arg4

*hRTDepthStencilView* [in]

A handle to the depth stencil view that the driver should use anytime it calls back into the Direct3D runtime.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilview">DestroyDepthStencilView</a> function to destroy the handle that the <i>hDepthStencilView</i> parameter specifies.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilviewsize">CalcPrivateDepthStencilViewSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdepthstencilview">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroydepthstencilview">DestroyDepthStencilView</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

