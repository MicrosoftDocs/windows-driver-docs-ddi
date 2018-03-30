---
UID: NC:d3d10umddi.PFND3D10DDI_OPENRESOURCE
title: PFND3D10DDI_OPENRESOURCE
author: windows-driver-content
description: The OpenResource(D3D10) function opens a shared resource.
old-location: display\openresource_d3d10_.htm
old-project: display
ms.assetid: 95f6d1e5-0c85-41ce-ad6d-f10d5103e2eb
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OpenResource, OpenResource callback function [Display Devices], PFND3D10DDI_OPENRESOURCE, UserModeDisplayDriverDx10_Functions_ea9696b9-fb0f-4feb-be35-db3e59c74b4e.xml, d3d10umddi/OpenResource, display.openresource_d3d10_
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
-	OpenResource
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_OPENRESOURCE callback


## -description


The <i>OpenResource(D3D10)</i> function opens a shared resource.


## -parameters




### -param Arg1


### -param *


### -param Arg2


### -param Arg3








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hRTResource [in]

 A handle to the resource that the driver should use anytime it calls back into the Direct3D runtime. 


#### - hResource [in]

 A handle to the driver's private data for the resource. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/000688fb-6475-4dab-bb65-91c899a592a7">CalcPrivateOpenedResourceSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its resource object. 


#### - pOpenResource [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541736">D3D10DDIARG_OPENRESOURCE</a> structure that describes the parameters that the user-mode display driver uses to open a shared resource. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/3ff77844-eeee-4fda-8798-2e240bc51379">DestroyResource(D3D10)</a> function to destroy the handle that the <i>hResource</i> parameter specifies.




## -see-also




<a href="https://msdn.microsoft.com/000688fb-6475-4dab-bb65-91c899a592a7">CalcPrivateOpenedResourceSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541736">D3D10DDIARG_OPENRESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/3ff77844-eeee-4fda-8798-2e240bc51379">DestroyResource(D3D10)</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

