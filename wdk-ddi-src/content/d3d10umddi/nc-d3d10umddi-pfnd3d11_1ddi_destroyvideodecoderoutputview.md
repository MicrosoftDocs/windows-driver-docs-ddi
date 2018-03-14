---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW
title: PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW
author: windows-driver-content
description: Releases resources for the video decoder output view that were created through a call to the CreateVideoDecoderOutputView function.
old-location: display\destroyvideodecoderoutputview.htm
old-project: display
ms.assetid: acb174e5-09cc-41e9-8b30-8c64f6193f7b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW, d3d10umddi/pfnDestroyVideoDecoderOutputView, display.destroyvideodecoderoutputview, pfnDestroyVideoDecoderOutputView, pfnDestroyVideoDecoderOutputView callback function [Display Devices]
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
-	pfnDestroyVideoDecoderOutputView
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW callback


## -description


Releases resources for the video decoder output view that were created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview.md">CreateVideoDecoderOutputView</a> function.



## -prototype


````
PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW pfnDestroyVideoDecoderOutputView;

VOID APIENTRY* pfnDestroyVideoDecoderOutputView(
  _In_ D3D10DDI_HDEVICE                   hDevice,
       D3D11_1DDI_HVIDEODECODEROUTPUTVIEW hView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D11_1DDI_HVIDEODECODEROUTPUTVIEW








#### - hDevice [in]

A handle to the display device (graphics context).




#### - hView

A handle to the driver's private data for the video decoder output view. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview.md">CreateVideoDecoderOutputView</a>.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview.md">CreateVideoDecoderOutputView</a>



 

 


