---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEBLENDSTATE
title: PFND3D10DDI_CREATEBLENDSTATE (d3d10umddi.h)
description: The CreateBlendState function creates a blend state.
old-location: display\createblendstate.htm
ms.assetid: f203a83c-0108-4e20-9972-06857099378c
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CREATEBLENDSTATE callback function"]
ms.keywords: CreateBlendState, CreateBlendState callback function [Display Devices], PFND3D10DDI_CREATEBLENDSTATE, PFND3D10DDI_CREATEBLENDSTATE callback, UserModeDisplayDriverDx10_Functions_5c67ddaf-f8a2-4529-8684-1f0298221a8d.xml, d3d10umddi/CreateBlendState, display.createblendstate
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
 - "d3d10umddi/CreateBlendState"
 - "CreateBlendState"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CreateBlendState
product:
 - Windows
---

# PFND3D10DDI_CREATEBLENDSTATE callback function

## -description

The <b>CreateBlendState</b> function creates a blend state.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pBlendDesc* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_blend_desc">D3D10_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a blend state.

### -param Arg3

*hBlendState* [in]

A handle to the driver's private data for the blend state.

### -param Arg4

*hRTBlendState* [in]

A handle to the blend state that the driver should use anytime it calls back into the Direct3D runtime.

## -remarks

The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyblendstate">DestroyBlendState</a> function to destroy the handle that the <i>hBlendState</i> parameter specifies.

The user-mode display driver is not required to create more than 4,096 unique instances of blend-state objects on a device at one time.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateblendstatesize">CalcPrivateBlendStateSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_blend_desc">D3D10_DDI_BLEND_DESC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyblendstate">DestroyBlendState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

