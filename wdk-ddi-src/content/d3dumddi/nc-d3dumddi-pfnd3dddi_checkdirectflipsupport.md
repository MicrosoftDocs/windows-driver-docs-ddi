---
UID: NC:d3dumddi.PFND3DDDI_CHECKDIRECTFLIPSUPPORT
title: PFND3DDDI_CHECKDIRECTFLIPSUPPORT
author: windows-driver-content
description: Called by the Desktop Window Manager (DWM) to verify that the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the DWM's managed primary allocations.
old-location: display\checkdirectflipsupport.htm
tech.root: display
ms.assetid: BB909041-0194-4828-ACA2-E3F6B1974DBB
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CheckDirectFlipSupport, CheckDirectFlipSupport callback function [Display Devices], PFND3DDDI_CHECKDIRECTFLIPSUPPORT, PFND3DDDI_CHECKDIRECTFLIPSUPPORT callback, d3dumddi/CheckDirectFlipSupport, display.checkdirectflipsupport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	CheckDirectFlipSupport
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CHECKDIRECTFLIPSUPPORT callback function


## -description


Called by the Desktop Window Manager (DWM) to verify that the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the DWM's managed primary allocations.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451072">D3DDDIARG_CHECKDIRECTFLIPSUPPORT</a> structure that defines the parameters for the operation.


## -returns




      Returns S_OK or an appropriate error result if the operation is not successfully performed.




## -remarks



This function is called at least once before the DWM attempts to present to a Direct Flip swapchain. It is also called after each mode change occurs, or after the DWM re-creates its own swapchain for any reason.

The user-mode driver should ensure that the managed primary allocations of the application and the DWM have the following compatible resources:

<ul>
<li>Stereo resources.</li>
<li>Multiple Sample Anti Aliasing (MSAA) formats.</li>
<li>Swizzle formats. If the swizzle can only be changed at every VSync interval, ensure that the <i>CheckDirectFlipFlags</i> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451172">D3DDDI_CHECK_DIRECT_FLIP_FLAGS</a> structure does not have a value of <b>D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE</b>.</li>
<li>Both managed primary allocations should be created using the same <b>VidPnSourceId</b> value in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544364">D3DDDI_ALLOCATIONINFO</a> structure.</li>
<li>Display adapter configurations are linked.</li>
</ul>
The user-mode driver might need to call the kernel-mode driver to perform these validations. To do this, call the <a href="https://msdn.microsoft.com/66c0347f-2cf3-42fc-8641-47c731e958c9">pfnEscapeCb</a> callback function and then call the <a href="https://msdn.microsoft.com/144429e5-34e6-4416-980e-2838e8f9e415">DxgkCbGetHandleData</a> function to access the kernel-mode driver's resource allocation data.

Because the DWM typically creates its own device using the highest possible Microsoft Direct3D feature level, the DWM will not call this function if the hardware supports a Direct3D device driver interface (DDI) that is greater than version 9.3. However, any Microsoft Direct3D 9 driver should implement this function to enable the Direct Flip user experience.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451172">D3DDDI_CHECK_DIRECT_FLIP_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 

