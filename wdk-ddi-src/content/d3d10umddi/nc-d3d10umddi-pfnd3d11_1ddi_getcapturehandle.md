---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETCAPTUREHANDLE
title: PFND3D11_1DDI_GETCAPTUREHANDLE
author: windows-driver-content
description: Returns the handle for a specified resource that was allocated by the driver. This function also returns the size and location of specified data within the resource.
old-location: display\getcapturehandle.htm
old-project: display
ms.assetid: b1ca7cf0-fe63-452f-8360-fdba05875719
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: GetCaptureHandle, GetCaptureHandle callback function [Display Devices], PFND3D11_1DDI_GETCAPTUREHANDLE, PFND3D11_1DDI_GETCAPTUREHANDLE callback, d3d10umddi/GetCaptureHandle, display.getcapturehandle
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
-	GetCaptureHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_GETCAPTUREHANDLE callback function


## -description


Returns the handle for a specified resource that was allocated by the driver. This function also returns the size and location of specified data within the resource.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *pHandleData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406448">D3D11_1DDI_GETCAPTUREHANDLEDATA</a> structure that defines the resource allocation. 


## -returns



This callback function does not return a value.




## -remarks



Before the Microsoft Direct3D runtime calls the <i>GetCaptureHandle</i> function, it sets the <b>hResource</b>  and <b>ArrayIndex</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406448">D3D11_1DDI_GETCAPTUREHANDLEDATA</a> structure to specify a resource. When this function is called, the driver updates the structure with the kernel mode allocation handle associated with the specified resource, as well as the size of the resource data and its offset within an allocated block of memory.

<div class="alert"><b>Note</b>  The Direct3D runtime calls this function only for resources that were created with the <b>D3D11_DDI_BIND_CAPTURE</b> flag.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406448">D3D11_1DDI_GETCAPTUREHANDLEDATA</a>
 

 

