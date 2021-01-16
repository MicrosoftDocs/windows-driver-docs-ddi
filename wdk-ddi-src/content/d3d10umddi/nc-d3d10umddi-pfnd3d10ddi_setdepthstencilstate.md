---
UID: NC:d3d10umddi.PFND3D10DDI_SETDEPTHSTENCILSTATE
title: PFND3D10DDI_SETDEPTHSTENCILSTATE (d3d10umddi.h)
description: The SetDepthStencilState function sets a depth-stencil state.
old-location: display\setdepthstencilstate.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_SETDEPTHSTENCILSTATE callback function"]
ms.keywords: PFND3D10DDI_SETDEPTHSTENCILSTATE, PFND3D10DDI_SETDEPTHSTENCILSTATE callback, SetDepthStencilState, SetDepthStencilState callback function [Display Devices], UserModeDisplayDriverDx10_Functions_850fde8e-3bb5-4943-94ba-d98298599c19.xml, d3d10umddi/SetDepthStencilState, display.setdepthstencilstate
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
 - PFND3D10DDI_SETDEPTHSTENCILSTATE
 - d3d10umddi/PFND3D10DDI_SETDEPTHSTENCILSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_SETDEPTHSTENCILSTATE
---

# PFND3D10DDI_SETDEPTHSTENCILSTATE callback function


## -description

The <i>SetDepthStencilState</i> function sets a depth-stencil state.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hState* [in]

A handle to the depth-stencil state to set.

### -param Arg3

*StencilRef* [in]

A stencil reference value to compare against.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>SetDepthStencilState</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

