---
UID: NC:d3dumddi.PFND3DDDI_DESTROYRESOURCE
title: PFND3DDDI_DESTROYRESOURCE
author: windows-driver-content
description: The DestroyResource function releases a specified resource.
old-location: display\destroyresource.htm
old-project: display
ms.assetid: 1af85315-4367-49de-9453-eef62c838c97
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DestroyResource, DestroyResource callback function [Display Devices], PFND3DDDI_DESTROYRESOURCE, UserModeDisplayDriver_Functions_7d6c0444-aa22-4348-9da4-9708414284e9.xml, d3dumddi/DestroyResource, display.destroyresource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	DestroyResource
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DESTROYRESOURCE callback


## -description


The <b>DestroyResource</b> function releases a specified resource.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context) that is used to destroy the resource.


### -param Arg1








#### - hResource [in]

 A handle to the resource that the <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> or <a href="https://msdn.microsoft.com/e3f5cec2-391b-40f9-8a4b-afe6b8de2954">OpenResource</a> function created.


## -returns



<b>DestroyResource</b> returns S_OK or an appropriate error result is the resource is not released. 




## -remarks



After the Microsoft Direct3D runtime calls the user-mode display driver's <b>DestroyResource</b> function, the user-mode display driver must first flush any batched commands that depend on the resource that is being destroyed by calling the runtime's <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a> function. The driver must then call the runtime's <a href="https://msdn.microsoft.com/2ffa0367-0451-45d2-be05-e450c45be116">pfnDeallocateCb</a> function to destroy allocations that are associated with the resource. 

<div class="alert"><b>Note</b>    The driver's <b>DestroyResource</b> function is not required to call <a href="https://msdn.microsoft.com/2ffa0367-0451-45d2-be05-e450c45be116">pfnDeallocateCb</a> before returning; instead, the driver can defer allocation destruction.</div>
<div> </div>
<div class="alert"><b>Note</b>    A separate <b>DestroyResource</b> call is not made for each surface that is part of the resource. So, if a group of surfaces is atomically created, the group is always atomically destroyed as well. </div>
<div> </div>
For more information about creating and destroying resources, see <a href="https://msdn.microsoft.com/d443bdc3-1c5a-4372-9e6a-b8a4d21499b9">Handling Resource Creation and Destruction</a>.




## -see-also




<a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/e3f5cec2-391b-40f9-8a4b-afe6b8de2954">OpenResource</a>



<a href="https://msdn.microsoft.com/2ffa0367-0451-45d2-be05-e450c45be116">pfnDeallocateCb</a>



<a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a>
 

 

