---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEDEPTHSTENCILVIEW
title: PFND3D10DDI_CREATEDEPTHSTENCILVIEW
author: windows-driver-content
description: The CreateDepthStencilView function creates a depth stencil view.
old-location: display\createdepthstencilview.htm
old-project: display
ms.assetid: 1a1c28f0-8343-4255-8055-d31eb643b7d5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CreateDepthStencilView, CreateDepthStencilView callback function [Display Devices], PFND3D10DDI_CREATEDEPTHSTENCILVIEW, UserModeDisplayDriverDx10_Functions_299a6bcd-ba94-4568-a4fc-d89c84742c45.xml, d3d10umddi/CreateDepthStencilView, display.createdepthstencilview
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
-	CreateDepthStencilView
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CREATEDEPTHSTENCILVIEW callback


## -description


The <b>CreateDepthStencilView</b> function creates a depth stencil view.


## -parameters




### -param Arg1


### -param *


### -param Arg2


### -param Arg3








#### - hDepthStencilView [in]

 A handle to the driver's private data for the depth stencil view. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/e5dfa018-f9a5-467f-8e84-9697d5f94689">CalcPrivateDepthStencilViewSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its depth stencil view object.


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hRTDepthStencilView [in]

 A handle to the depth stencil view that the driver should use anytime it calls back into the Direct3D runtime. 


#### - pCreateDepthStencilView [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541658">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a> structure that describes the parameters that the user-mode display driver uses to create a depth stencil view. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/5cd2b7bd-0231-4f00-a54e-960b9bffa98e">DestroyDepthStencilView</a> function to destroy the handle that the <i>hDepthStencilView</i> parameter specifies.




## -see-also




<a href="https://msdn.microsoft.com/e5dfa018-f9a5-467f-8e84-9697d5f94689">CalcPrivateDepthStencilViewSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541658">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/5cd2b7bd-0231-4f00-a54e-960b9bffa98e">DestroyDepthStencilView</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

