---
UID: NC:d3d10umddi.PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT
title: PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT
author: windows-driver-content
description: Called by the Desktop Window Manager (DWM) to verify that the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the DWM's managed primary allocations.
old-location: display\checkdirectflipsupport_d3d11_1_.htm
old-project: display
ms.assetid: 2acf84cb-5e51-4aa8-96ce-96abc6ceec8c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CheckDirectFlipSupport(D3D11_1), CheckDirectFlipSupport(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT, d3d10umddi/CheckDirectFlipSupport(D3D11_1), display.checkdirectflipsupport_d3d11_1_, display.pfncheckdirectflipsupport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	CheckDirectFlipSupport(D3D11_1)
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT callback


## -description


Called by the Desktop Window Manager (DWM) to verify that the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the DWM's managed primary allocations.


## -parameters




### -param Arg1


### -param Arg2


### -param Arg3


### -param CheckDirectFlipFlags

If this parameter has a value of <b>D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE</b>, seamless flipping should occur immediately and does not have to be synchronized with a VSync interrupt.


### -param *pSupported [out]

Set to <b>TRUE</b> if the driver can seamlessly flip video memory between  an application's managed primary allocations and the DWM's managed primary allocations. Otherwise, set to <b>FALSE</b>.


#### - hDevice

A handle to the display device (graphics context).


#### - hResource1

A resource in the application's swapchain.


#### - hResource2

A resource in the DWM's swapchain.


## -returns



This callback function does not return a value.




## -remarks



This function is called at least once before the DWM attempts to present to a Direct Flip swapchain. It is also called after each mode change occurs, or after the DWM re-creates its own swapchain for any reason.

The user-mode driver should ensure that the managed primary allocations of the application and the DWM have the following compatible resources:

<ul>
<li>Stereo resources.</li>
<li>Multiple Sample Anti Aliasing (MSAA) formats.</li>
<li>Swizzle formats. If the swizzle can only be changed at every VSync interval, ensure that the <i>CheckDirectFlipFlags</i> parameter does not have a value of <b>D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE</b>.</li>
<li>Both managed primary allocations should be created using the same <b>VidPnSourceId</b> value in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544364">D3DDDI_ALLOCATIONINFO</a> structure.</li>
<li>Display adapter configurations are linked.</li>
</ul>
The user-mode driver might need to call the kernel-mode driver to perform these validations. To do this, call the <a href="https://msdn.microsoft.com/66c0347f-2cf3-42fc-8641-47c731e958c9">pfnEscapeCb</a> callback function and then call the <a href="https://msdn.microsoft.com/144429e5-34e6-4416-980e-2838e8f9e415">DxgkCbGetHandleData</a> function to access the kernel-mode driver's resource allocation data.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451044">D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544364">D3DDDI_ALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/144429e5-34e6-4416-980e-2838e8f9e415">DxgkCbGetHandleData</a>



<a href="https://msdn.microsoft.com/66c0347f-2cf3-42fc-8641-47c731e958c9">pfnEscapeCb</a>
 

 

