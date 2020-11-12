---
UID: NC:d3d10umddi.PFND3D10DDI_SETRENDERTARGETS
title: PFND3D10DDI_SETRENDERTARGETS (d3d10umddi.h)
description: The SetRenderTargets function sets render target surfaces.
old-location: display\setrendertargets.htm
ms.assetid: 852893e6-1f1c-470a-ab72-f52c1e06e0c0
ms.date: 10/16/2020
keywords: ["PFND3D10DDI_SETRENDERTARGETS callback function"]
ms.keywords: PFND3D10DDI_SETRENDERTARGETS, PFND3D10DDI_SETRENDERTARGETS callback, SetRenderTargets, SetRenderTargets callback function [Display Devices], UserModeDisplayDriverDx10_Functions_6d202eaa-50bb-4ffd-9217-a0c172974e49.xml, d3d10umddi/SetRenderTargets, display.setrendertargets
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
 - PFND3D10DDI_SETRENDERTARGETS
 - d3d10umddi/PFND3D10DDI_SETRENDERTARGETS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - SetRenderTargets
product:
 - Windows
---

# PFND3D10DDI_SETRENDERTARGETS callback function

## -description

The **SetRenderTargets** callback function sets render target surfaces.

## -parameters

### -param Arg1

[in] **hDevice**: A handle to the display device (graphics context).

### -param Arg2

[in] **phRenderTargetView**: An array of handles to the render target view objects to set. Note that some handle values can be **NULL**.

### -param NumViews

[in] : The number of elements in the array that **phRenderTargetView** specifies.

### -param ClearSlots

[in] The number of render target slots after the number of slots that **NumViews** specifies to be set to **NULL**. This number represents the difference between the previous number of render target view objects (that is, when the Microsoft Direct3D runtime previously called **SetRenderTargets**) and the new number of render target view objects.

Note that the number that **ClearTargets** specifies is only an optimization aid because the user-mode display driver could calculate this number.

### -param Arg5

[in] **hDepthStencilView**: Handle to the depth stencil view.

## -remarks

The driver can use the [**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md) callback function to set an error code.

The user-mode display driver must set all render target surfaces and the depth stencil buffer atomically as one operation.

Although the **NumViews** parameter specifies the number of handles in the array that the **phRenderTargetView** parameter specifies, some handle values in the array can be **NULL**.

The range of render target surfaces between the number that **NumViews** specifies and the maximum number of render target surfaces that are allowed is required to contain all **NULL** or unbound values. The number that the **ClearTargets** parameter specifies informs the driver about how many bind points the driver must clear out for the current atomic operation.

If the previous call to **SetRenderTargets** passed a value of 2 in the **NumViews** parameter and the current call to **SetRenderTargets** passes a value of 4 in **NumViews**, the current call to **SetRenderTargets** also passes a value of 0 in the **ClearTargets** parameter. If the next successive call to **SetRenderTargets** passes a value of 1 in **NumViews**, the successive call also passes a value of 3 (4 - 1) in **ClearTargets**.

When the value of clear targets is requested during user-mode query operations, the value is the difference between the maximum number of render target surfaces and the render targets value.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the [**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md) function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of **SetRenderTargets** (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

[**D3D10DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d10ddi_devicefuncs.md)

[**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md)
