---
UID: NC:d3d10umddi.PFND3D10DDI_SETBLENDSTATE
title: PFND3D10DDI_SETBLENDSTATE (d3d10umddi.h)
description: The SetBlendState function sets a blend state.
old-location: display\setblendstate.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_SETBLENDSTATE callback function"]
ms.keywords: PFND3D10DDI_SETBLENDSTATE, PFND3D10DDI_SETBLENDSTATE callback, SetBlendState, SetBlendState callback function [Display Devices], UserModeDisplayDriverDx10_Functions_11dcf032-7cd6-497e-985d-548960276981.xml, d3d10umddi/SetBlendState, display.setblendstate
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
 - PFND3D10DDI_SETBLENDSTATE
 - d3d10umddi/PFND3D10DDI_SETBLENDSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_SETBLENDSTATE
product:
 - Windows
---

# PFND3D10DDI_SETBLENDSTATE callback function


## -description

The <i>SetBlendState</i> function sets a blend state.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hState* [in]

A handle to the blend state to set.

### -param FLOAT

[4]
*pBlendFactor* [in]

A four-element array of single-precision float vectors that the driver uses to set the blend state.

### -param Arg4

*SampleMask* [in]

A sample format mask.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>SetBlendState</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

