---
UID: NC:d3dumddi.PFND3DDDI_DESTROYRESOURCE
title: PFND3DDDI_DESTROYRESOURCE
author: windows-driver-content
description: The DestroyResource function releases a specified resource.
old-location: display\destroyresource.htm
old-project: display
ms.assetid: 1af85315-4367-49de-9453-eef62c838c97
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.destroyresource, DestroyResource callback function [Display Devices], DestroyResource, PFND3DDDI_DESTROYRESOURCE, PFND3DDDI_DESTROYRESOURCE, d3dumddi/DestroyResource, UserModeDisplayDriver_Functions_7d6c0444-aa22-4348-9da4-9708414284e9.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	DestroyResource
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DESTROYRESOURCE callback


## -description


The <b>DestroyResource</b> function releases a specified resource.


## -prototype


````
PFND3DDDI_DESTROYRESOURCE DestroyResource;

__checkReturn HRESULT APIENTRY DestroyResource(
  _In_ HANDLE hDevice,
  _In_ HANDLE hResource
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context) that is used to destroy the resource.


### -param HANDLE








#### - hResource [in]

 A handle to the resource that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> or <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openresource.md">OpenResource</a> function created.


## -returns



<b>DestroyResource</b> returns S_OK or an appropriate error result is the resource is not released. 




## -remarks



After the Microsoft Direct3D runtime calls the user-mode display driver's <b>DestroyResource</b> function, the user-mode display driver must first flush any batched commands that depend on the resource that is being destroyed by calling the runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a> function. The driver must then call the runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a> function to destroy allocations that are associated with the resource. 

<div class="alert"><b>Note</b>    The driver's <b>DestroyResource</b> function is not required to call <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a> before returning; instead, the driver can defer allocation destruction.</div>
<div> </div>
<div class="alert"><b>Note</b>    A separate <b>DestroyResource</b> call is not made for each surface that is part of the resource. So, if a group of surfaces is atomically created, the group is always atomically destroyed as well. </div>
<div> </div>
For more information about creating and destroying resources, see <a href="https://msdn.microsoft.com/d443bdc3-1c5a-4372-9e6a-b8a4d21499b9">Handling Resource Creation and Destruction</a>.




## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openresource.md">OpenResource</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYRESOURCE callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

