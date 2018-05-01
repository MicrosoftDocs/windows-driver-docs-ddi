---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEBLENDSTATE
title: PFND3D11_1DDI_CREATEBLENDSTATE
author: windows-driver-content
description: Creates a blend state.
old-location: display\createblendstate_d3d11_1_.htm
old-project: display
ms.assetid: 5956412e-ae35-4960-afc0-a82c6a2aa9f1
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CreateBlendState(D3D11_1), CreateBlendState(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CREATEBLENDSTATE, PFND3D11_1DDI_CREATEBLENDSTATE callback, d3d10umddi/CreateBlendState(D3D11_1), display.createblendstate_d3d11_1_, display.pfncreateblendstate
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
-	CreateBlendState(D3D11_1)
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_CREATEBLENDSTATE callback function


## -description


Creates a blend state.


## -parameters




### -param Arg1


### -param *


### -param Arg2


### -param Arg3








#### - [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451041">D3D11_1_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a blend state.


#### - hBlendState

A handle to the driver's private data for the blend state. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/e53bb658-ef6c-4f44-aa5a-8c641046f90d">CalcPrivateBlendStateSize(D3D11_1)</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its blend state object.


#### - hDevice

A handle to the display device (graphics context).




#### - hRTBlendState

A handle to the blend state that the driver should use when it calls back into the Direct3D runtime.


## -returns



The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section.




## -remarks



The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is incorrect; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/56fc1ecf-fd4c-4d36-941b-8fa6cca3b6b4">DestroyBlendState</a> function to destroy the handle that the <i>hBlendState</i> parameter specifies.

The user-mode display driver is not required to create more than 4,096 unique instances of blend-state objects on a device at one time.




## -see-also




<a href="https://msdn.microsoft.com/e53bb658-ef6c-4f44-aa5a-8c641046f90d">CalcPrivateBlendStateSize(D3D11_1)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451041">D3D11_1_DDI_BLEND_DESC</a>



<a href="https://msdn.microsoft.com/56fc1ecf-fd4c-4d36-941b-8fa6cca3b6b4">DestroyBlendState</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

