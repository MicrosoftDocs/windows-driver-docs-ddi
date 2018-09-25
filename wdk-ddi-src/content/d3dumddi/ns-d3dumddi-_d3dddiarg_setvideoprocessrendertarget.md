---
UID: NS:d3dumddi._D3DDDIARG_SETVIDEOPROCESSRENDERTARGET
title: "_D3DDDIARG_SETVIDEOPROCESSRENDERTARGET"
author: windows-driver-content
description: The D3DDDIARG_SETVIDEOPROCESSRENDERTARGET structure describes the render target surface for video processing.
old-location: display\d3dddiarg_setvideoprocessrendertarget.htm
tech.root: display
ms.assetid: f92aebbf-f163-45fa-ad8e-c13a36f08458
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDIARG_SETVIDEOPROCESSRENDERTARGET, D3DDDIARG_SETVIDEOPROCESSRENDERTARGET structure [Display Devices], UMDisplayDriver_param_Structs_8a00fe2d-be28-4577-831f-45fbdcfbbb1d.xml, _D3DDDIARG_SETVIDEOPROCESSRENDERTARGET, d3dumddi/D3DDDIARG_SETVIDEOPROCESSRENDERTARGET, display.d3dddiarg_setvideoprocessrendertarget
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_SETVIDEOPROCESSRENDERTARGET
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_SETVIDEOPROCESSRENDERTARGET
---

# _D3DDDIARG_SETVIDEOPROCESSRENDERTARGET structure


## -description


The D3DDDIARG_SETVIDEOPROCESSRENDERTARGET structure describes the render target surface for video processing. 


## -struct-fields




### -field hVideoProcess

[in] A handle to the Microsoft DirectX Video Acceleration (DirectX VA) video processing device. The user-mode display driver returns this handle in a call to its <a href="https://msdn.microsoft.com/3149c7d9-0bf7-4355-8f15-821cf6b92f0a">CreateVideoProcessDevice</a> function.


### -field hRenderTarget

[in] A handle to the render target surface for video processing.


### -field SubResourceIndex

[in] An index into the resource for the render target surface.


## -see-also




<a href="https://msdn.microsoft.com/3149c7d9-0bf7-4355-8f15-821cf6b92f0a">CreateVideoProcessDevice</a>



<a href="https://msdn.microsoft.com/8aa7e23e-f52e-4252-9f22-56ce523f6cba">SetVideoProcessRenderTarget</a>
 

 

