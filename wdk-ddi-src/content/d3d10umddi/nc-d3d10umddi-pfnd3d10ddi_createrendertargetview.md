---
UID: NC:d3d10umddi.PFND3D10DDI_CREATERENDERTARGETVIEW
title: PFND3D10DDI_CREATERENDERTARGETVIEW (d3d10umddi.h)
description: The CreateRenderTargetView function creates a render target view.
old-location: display\createrendertargetview.htm
ms.assetid: bf9fc732-5f9a-4fee-8ea0-19b140789463
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CREATERENDERTARGETVIEW callback function"]
ms.keywords: CreateRenderTargetView, CreateRenderTargetView callback function [Display Devices], PFND3D10DDI_CREATERENDERTARGETVIEW, PFND3D10DDI_CREATERENDERTARGETVIEW callback, UserModeDisplayDriverDx10_Functions_abef4fc8-0aac-40a9-9f45-de2160c347af.xml, d3d10umddi/CreateRenderTargetView, display.createrendertargetview
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
 - PFND3D10DDI_CREATERENDERTARGETVIEW
 - d3d10umddi/PFND3D10DDI_CREATERENDERTARGETVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CreateRenderTargetView
product:
 - Windows
---

# PFND3D10DDI_CREATERENDERTARGETVIEW callback function


## -description

The <b>CreateRenderTargetView</b> function creates a render target view.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateRenderTargetView* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createrendertargetview">D3D10DDIARG_CREATERENDERTARGETVIEW</a> structure that describes the parameters that the user-mode display driver uses to create a render target view.

### -param Arg3

*hRenderTargetView* [in]

A handle to the driver's private data for the render target view.

### -param Arg4

*hRTRenderTargetView* [in]

A handle to the render target view that the driver should use anytime it calls back into the Direct3D runtime.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyrendertargetview">DestroyRenderTargetView</a> function to destroy the handle that the <i>hRenderTargetView</i> parameter specifies.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize">CalcPrivateRenderTargetViewSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createrendertargetview">D3D10DDIARG_CREATERENDERTARGETVIEW</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyrendertargetview">DestroyRenderTargetView</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>