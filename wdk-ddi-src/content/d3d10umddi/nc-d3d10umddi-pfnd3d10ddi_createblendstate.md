---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEBLENDSTATE
title: PFND3D10DDI_CREATEBLENDSTATE
author: windows-driver-content
description: The CreateBlendState function creates a blend state.
old-location: display\createblendstate.htm
tech.root: display
ms.assetid: f203a83c-0108-4e20-9972-06857099378c
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CreateBlendState, CreateBlendState callback function [Display Devices], PFND3D10DDI_CREATEBLENDSTATE, PFND3D10DDI_CREATEBLENDSTATE callback, UserModeDisplayDriverDx10_Functions_5c67ddaf-f8a2-4529-8684-1f0298221a8d.xml, d3d10umddi/CreateBlendState, display.createblendstate
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
-	CreateBlendState
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D10DDI_CREATEBLENDSTATE callback function


## -description


The <b>CreateBlendState</b> function creates a blend state.


## -parameters




### -param Arg1


### -param *


### -param Arg2


### -param Arg3








#### - hBlendState [in]

 A handle to the driver's private data for the blend state. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/c13862b0-3136-4a95-bb00-6057f2934068">CalcPrivateBlendStateSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its blend state object. 


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hRTBlendState [in]

 A handle to the blend state that the driver should use anytime it calls back into the Direct3D runtime. 


#### - pBlendDesc [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541919">D3D10_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a blend state. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/56fc1ecf-fd4c-4d36-941b-8fa6cca3b6b4">DestroyBlendState</a> function to destroy the handle that the <i>hBlendState</i> parameter specifies.

The user-mode display driver is not required to create more than 4,096 unique instances of blend-state objects on a device at one time. 




## -see-also




<a href="https://msdn.microsoft.com/c13862b0-3136-4a95-bb00-6057f2934068">CalcPrivateBlendStateSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541919">D3D10_DDI_BLEND_DESC</a>



<a href="https://msdn.microsoft.com/56fc1ecf-fd4c-4d36-941b-8fa6cca3b6b4">DestroyBlendState</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

