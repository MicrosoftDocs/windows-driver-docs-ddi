---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW
title: PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW
author: windows-driver-content
description: Creates a resource view for a video decoder. This view defines the output sample for the video decoding operation.
old-location: display\createvideodecoderoutputview.htm
ms.assetid: a5a32b4e-799c-4d18-995d-f804e6dff85c
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CreateVideoDecoderOutputView, CreateVideoDecoderOutputView callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW, PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW callback, d3d10umddi/CreateVideoDecoderOutputView, display.createvideodecoderoutputview
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
-	CreateVideoDecoderOutputView
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW callback function


## -description


Creates a resource view for a video decoder. This view defines the output sample for the video decoding operation.


## -parameters




### -param Arg1


### -param *


### -param Arg2


### -param Arg3








#### - hDevice [in]

A handle to the display device (graphics context).




#### - hRTView [in]

A handle to the video decoder output view that the driver should use when it calls back into the Direct3D runtime.


#### - hView [in]

A handle to the driver's private data for the video decoder output view. For more information, see the Remarks section.


#### - pCreateData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406312">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a> structure. This structure specifies the attributes of the video decoder output view to be created.


## -returns



<b>CreateVideoDecoderOutputView</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The video decoder output view was created successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was removed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table>
 




## -remarks



The Direct3D runtime calls <i>CreateVideoDecoderOutputView</i> after it has called the driver's <a href="https://msdn.microsoft.com/2cf09e91-e83b-47ae-bf34-037dc01d7e80">CalcPrivateVideoProcessorOutputViewSize</a>  to determine the size in bytes for the private data that the driver requires for the video decoder object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video decoder object.

When the runtime  calls <i>CreateVideoDecoderOutputView</i>, it passes the handle to the private data memory in the <i>hView</i> parameter. This handle is actually  a pointer to the memory. 




## -see-also




<a href="https://msdn.microsoft.com/2cf09e91-e83b-47ae-bf34-037dc01d7e80">CalcPrivateVideoProcessorOutputViewSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406310">D3D11_1DDIARG_CREATEVIDEODECODER</a>



<a href="https://msdn.microsoft.com/a48dcbae-3236-4523-bc14-4be694da9a7b">NegotiateCryptoSessionKeyExchange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a>
 

 

