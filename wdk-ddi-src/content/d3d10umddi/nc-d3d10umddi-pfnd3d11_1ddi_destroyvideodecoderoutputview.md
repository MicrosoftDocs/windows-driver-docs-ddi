---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW
title: PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW
author: windows-driver-content
description: Releases resources for the video decoder output view that were created through a call to the CreateVideoDecoderOutputView function.
old-location: display\destroyvideodecoderoutputview.htm
old-project: display
ms.assetid: acb174e5-09cc-41e9-8b30-8c64f6193f7b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.destroyvideodecoderoutputview, pfnDestroyVideoDecoderOutputView callback function [Display Devices], pfnDestroyVideoDecoderOutputView, PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW, PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW, d3d10umddi/pfnDestroyVideoDecoderOutputView
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	D3d10umddi.h
apiname: 
-	pfnDestroyVideoDecoderOutputView
product: Windows
targetos: Windows
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
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






#### - hView

A handle to the driver's private data for the video decoder output view. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview.md">CreateVideoDecoderOutputView</a>.


#### - hDevice [in]

A handle to the display device (graphics context).




## -returns


This callback function does not return a value.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview.md">CreateVideoDecoderOutputView</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_DESTROYVIDEODECODEROUTPUTVIEW callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

