---
UID: NC:d3d10umddi.PFND3D10DDI_SETRENDERTARGETS
title: PFND3D10DDI_SETRENDERTARGETS
author: windows-driver-content
description: The SetRenderTargets function sets render target surfaces.
old-location: display\setrendertargets.htm
tech.root: display
ms.assetid: 852893e6-1f1c-470a-ab72-f52c1e06e0c0
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D10DDI_SETRENDERTARGETS, PFND3D10DDI_SETRENDERTARGETS callback, SetRenderTargets, SetRenderTargets callback function [Display Devices], UserModeDisplayDriverDx10_Functions_6d202eaa-50bb-4ffd-9217-a0c172974e49.xml, d3d10umddi/SetRenderTargets, display.setrendertargets
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	SetRenderTargets
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D10DDI_SETRENDERTARGETS callback function


## -description


The <i>SetRenderTargets</i> function sets render target surfaces.


## -parameters




### -param Arg1


### -param *


### -param NumViews


### -param ClearSlots


### -param Arg2








#### - ClearTargets [in]

 The number of render target slots after the number of slots that <i>RTargets </i>specifies to be set to <b>NULL</b>. This number represents the difference between the previous number of render target view objects (that is, when the Microsoft Direct3D runtime previously called <i>SetRenderTargets</i>) and the new number of render target view objects. 

Note that the number that <i>ClearTargets</i> specifies is only an optimization aid because the user-mode display driver could calculate this number. 


#### - RTargets [in]

 The number of elements in the array that <i>phRenderTargetView</i> specifies. 


#### - hDepthStencilView [in]

 A handle to the depth stencil buffer to set. 


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - phRenderTargetView [in]

 An array of handles to the render target view objects to set. Note that some handle values can be <b>NULL</b>. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The user-mode display driver must set all render target surfaces and the depth stencil buffer atomically as one operation. 

Although the <i>RTargets</i> parameter specifies the number of handles in the array that the <i>phRenderTargetView</i> parameter specifies, some handle values in the array can be <b>NULL</b>. 

The range of render target surfaces between the number that <i>RTargets</i> specifies and the maximum number of render target surfaces that are allowed is required to contain all <b>NULL</b> or unbound values. The number that the <i>ClearTargets</i> parameter specifies informs the driver about how many bind points the driver must clear out for the current atomic operation. 

If the previous call to <i>SetRenderTargets</i> passed a value of 2 in the <i>RTargets</i> parameter and the current call to <i>SetRenderTargets</i> passes a value of 4 in <i>RTargets</i>, the current call to <i>SetRenderTargets</i> also passes a value of 0 in the <i>ClearTargets</i> parameter. If the next successive call to <i>SetRenderTargets</i> passes a value of 1 in <i>RTargets</i>, the successive call also passes a value of 3 (4 - 1) in <i>ClearTargets</i>.

When the value of clear targets is requested during user-mode query operations, the value is the difference between the maximum number of render target surfaces and the render targets value.

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>SetRenderTargets</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

