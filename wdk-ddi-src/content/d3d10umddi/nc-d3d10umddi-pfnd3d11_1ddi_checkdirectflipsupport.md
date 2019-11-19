---
UID: NC:d3d10umddi.PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT
title: PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT (d3d10umddi.h)
description: Called by the Desktop Window Manager (DWM) to verify that the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the DWM's managed primary allocations.
old-location: display\checkdirectflipsupport_d3d11_1_.htm
ms.assetid: 2acf84cb-5e51-4aa8-96ce-96abc6ceec8c
ms.date: 05/10/2018
ms.keywords: CheckDirectFlipSupport(D3D11_1), CheckDirectFlipSupport(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT, PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT callback, d3d10umddi/CheckDirectFlipSupport(D3D11_1), display.checkdirectflipsupport_d3d11_1_, display.pfncheckdirectflipsupport
ms.topic: callback
f1_keywords:
 - "d3d10umddi/CheckDirectFlipSupport(D3D11_1)"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- CheckDirectFlipSupport(D3D11_1)
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT callback function


## -description


Called by the Desktop Window Manager (DWM) to verify that the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the DWM's managed primary allocations.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hResource1*

A resource in the application's swapchain.

### -param Arg3

*hResource2*

A resource in the DWM's swapchain.

### -param CheckDirectFlipFlags

If this parameter has a value of <b>D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE</b>, seamless flipping should occur immediately and does not have to be synchronized with a VSync interrupt.


### -param pSupported [out]

Set to <b>TRUE</b> if the driver can seamlessly flip video memory between  an application's managed primary allocations and the DWM's managed primary allocations. Otherwise, set to <b>FALSE</b>.


## -remarks



This function is called at least once before the DWM attempts to present to a Direct Flip swapchain. It is also called after each mode change occurs, or after the DWM re-creates its own swapchain for any reason.

The user-mode driver should ensure that the managed primary allocations of the application and the DWM have the following compatible resources:

<ul>
<li>Stereo resources.</li>
<li>Multiple Sample Anti Aliasing (MSAA) formats.</li>
<li>Swizzle formats. If the swizzle can only be changed at every VSync interval, ensure that the <i>CheckDirectFlipFlags</i> parameter does not have a value of <b>D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE</b>.</li>
<li>Both managed primary allocations should be created using the same <b>VidPnSourceId</b> value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationinfo">D3DDDI_ALLOCATIONINFO</a> structure.</li>
<li>Display adapter configurations are linked.</li>
</ul>
The user-mode driver might need to call the kernel-mode driver to perform these validations. To do this, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_escapecb">pfnEscapeCb</a> callback function and then call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_gethandledata">DxgkCbGetHandleData</a> function to access the kernel-mode driver's resource allocation data.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1_ddi_check_direct_flip_flags">D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationinfo">D3DDDI_ALLOCATIONINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_gethandledata">DxgkCbGetHandleData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_escapecb">pfnEscapeCb</a>
 

 

