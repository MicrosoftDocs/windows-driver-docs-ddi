---
UID: NC:d3d10umddi.PFND3D10DDI_CLEARRENDERTARGETVIEW
title: PFND3D10DDI_CLEARRENDERTARGETVIEW (d3d10umddi.h)
description: The ClearRenderTargetView function clears the specified render-target view by setting it to a constant value.
old-location: display\clearrendertargetview.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CLEARRENDERTARGETVIEW callback function"]
ms.keywords: ClearRenderTargetView, ClearRenderTargetView callback function [Display Devices], PFND3D10DDI_CLEARRENDERTARGETVIEW, PFND3D10DDI_CLEARRENDERTARGETVIEW callback, UserModeDisplayDriverDx10_Functions_b9129a55-a400-45b7-a3a9-da477170c99c.xml, d3d10umddi/ClearRenderTargetView, display.clearrendertargetview
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
 - PFND3D10DDI_CLEARRENDERTARGETVIEW
 - d3d10umddi/PFND3D10DDI_CLEARRENDERTARGETVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - ClearRenderTargetView
---

# PFND3D10DDI_CLEARRENDERTARGETVIEW callback function


## -description

The <b>ClearRenderTargetView</b> function clears the specified render-target view by setting it to a constant value.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pColorRGBA* [in]

A four-element array of single-precision float vectors that the driver uses to clear a render-target view. Array element 0 is red (R), 1 is green (G), 2 is blue (B), and 3 is alpha (A).

### -param Arg3

*hRenderTargetView* [in]

A handle to the render-target view to clear.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>ClearRenderTargetView</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
