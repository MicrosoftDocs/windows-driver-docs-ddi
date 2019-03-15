---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW
title: PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW (d3d10umddi.h)
description: Releases resources for the video decoder output view that were created through a call to the CreateVideoDecoderOutputView function.
old-location: display\destroyvideodecoderoutputview.htm
ms.assetid: acb174e5-09cc-41e9-8b30-8c64f6193f7b
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW, PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW callback, d3d10umddi/pfnDestroyVideoDecoderOutputView, display.destroyvideodecoderoutputview, pfnDestroyVideoDecoderOutputView, pfnDestroyVideoDecoderOutputView callback function [Display Devices]
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- pfnDestroyVideoDecoderOutputView
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW callback function


## -description


Releases resources for the video decoder output view that were created through a call to the <a href="https://msdn.microsoft.com/a5a32b4e-799c-4d18-995d-f804e6dff85c">CreateVideoDecoderOutputView</a> function.



## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hView*

A handle to the driver's private data for the video decoder output view. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="https://msdn.microsoft.com/a5a32b4e-799c-4d18-995d-f804e6dff85c">CreateVideoDecoderOutputView</a>.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/a5a32b4e-799c-4d18-995d-f804e6dff85c">CreateVideoDecoderOutputView</a>
 

 

