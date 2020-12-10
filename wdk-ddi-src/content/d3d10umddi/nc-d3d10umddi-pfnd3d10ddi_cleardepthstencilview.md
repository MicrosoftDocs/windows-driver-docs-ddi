---
UID: NC:d3d10umddi.PFND3D10DDI_CLEARDEPTHSTENCILVIEW
title: PFND3D10DDI_CLEARDEPTHSTENCILVIEW (d3d10umddi.h)
description: The ClearDepthStencilView function clears the specified currently bound depth-stencil view.
old-location: display\cleardepthstencilview.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CLEARDEPTHSTENCILVIEW callback function"]
ms.keywords: ClearDepthStencilView, ClearDepthStencilView callback function [Display Devices], PFND3D10DDI_CLEARDEPTHSTENCILVIEW, PFND3D10DDI_CLEARDEPTHSTENCILVIEW callback, UserModeDisplayDriverDx10_Functions_580c85a3-3ad9-415c-925c-2ca103d10237.xml, d3d10umddi/ClearDepthStencilView, display.cleardepthstencilview
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
 - PFND3D10DDI_CLEARDEPTHSTENCILVIEW
 - d3d10umddi/PFND3D10DDI_CLEARDEPTHSTENCILVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - ClearDepthStencilView
---

# PFND3D10DDI_CLEARDEPTHSTENCILVIEW callback function


## -description

The **ClearDepthStencilView** function clears the specified currently bound depth-stencil view.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hDepthStencilView* [in]

A handle to the depth-stencil view to clear.

### -param Arg3

*Stencil* [in]

An unsigned 8-bit integer value to set the stencil to.

### -param Arg4

*Depth* [in]

A single-precision float vector to set the depth to.

### -param Arg5

*Flags* [in]

A value that specifies which parts of the buffer to affect. This parameter must be set to one of the following values from the D3D10_DDI_CLEAR_FLAG enumeration.

|Value|Meaning|
|:--|:--|
|D3D10_DDI_CLEAR_DEPTH (0x01L)|The depth value (Z) is clamped to the ZNear and ZFar range of the viewport that is currently bound to slot zero by using Microsoft Direct3D. Afterwards, Z is clamped again to the representable range of the currently bound depth-stencil view by again using Direct3D.|
|D3D10_DDI_CLEAR_STENCIL (0x02L)|The stencil value is cleared.|

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



Floating point rules apply to the <b>ClearDepthStencilView</b> function. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>ClearDepthStencilView</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
