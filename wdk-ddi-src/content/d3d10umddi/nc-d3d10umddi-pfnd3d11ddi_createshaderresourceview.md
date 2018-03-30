---
UID: NC:d3d10umddi.PFND3D11DDI_CREATESHADERRESOURCEVIEW
title: PFND3D11DDI_CREATESHADERRESOURCEVIEW
author: windows-driver-content
description: The CreateShaderResourceView(D3D11) function creates a shader resource view.
old-location: display\createshaderresourceview_d3d11_.htm
old-project: display
ms.assetid: 7ca462c7-ec43-4af7-92c8-ed69e5d324e2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateShaderResourceView, CreateShaderResourceView callback function [Display Devices], PFND3D11DDI_CREATESHADERRESOURCEVIEW, UserModeDisplayDriverDx11_Functions_abe7b0fb-121d-4486-af02-885ff37a4e81.xml, d3d10umddi/CreateShaderResourceView, display.createshaderresourceview_d3d11_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateShaderResourceView(D3D11) is supported beginning with the Windows 7 operating system.
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
-	CreateShaderResourceView
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_CREATESHADERRESOURCEVIEW callback


## -description


The <b>CreateShaderResourceView(D3D11)</b> function creates a shader resource view.


## -parameters




### -param Arg1


### -param *


### -param Arg2


### -param Arg3








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hRTShaderResourceView [in]

 A handle to the shader resource view that the driver should use when it calls back into the Direct3D runtime. 


#### - hShaderResourceView [in]

 A handle to the driver's private data for the shader resource view. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/894f6ef1-a5a4-40aa-9a07-f66da4ce7d81">CalcPrivateShaderResourceViewSize(D3D11)</a> function. The handle is  just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader resource view object. 


#### - pCreateShaderResourceView [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542073">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a> structure that describes the parameters that the user-mode display driver uses to create a shader resource view. 


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="https://msdn.microsoft.com/dcdfe76e-a392-4a76-91fe-03648fec1278">DestroyShaderResourceView</a> function to destroy the handle that the <i>hShaderResourceView</i> parameter specifies.




## -see-also




<a href="https://msdn.microsoft.com/894f6ef1-a5a4-40aa-9a07-f66da4ce7d81">CalcPrivateShaderResourceViewSize(D3D11)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542073">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/dcdfe76e-a392-4a76-91fe-03648fec1278">DestroyShaderResourceView</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 

