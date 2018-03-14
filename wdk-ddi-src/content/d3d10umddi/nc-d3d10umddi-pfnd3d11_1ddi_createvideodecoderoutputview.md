---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW
title: PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW
author: windows-driver-content
description: Creates a resource view for a video decoder. This view defines the output sample for the video decoding operation.
old-location: display\createvideodecoderoutputview.htm
old-project: display
ms.assetid: a5a32b4e-799c-4d18-995d-f804e6dff85c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateVideoDecoderOutputView, CreateVideoDecoderOutputView callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW, d3d10umddi/CreateVideoDecoderOutputView, display.createvideodecoderoutputview
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
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW callback


## -description


Creates a resource view for a video decoder. This view defines the output sample for the video decoding operation.


## -prototype


````
PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW CreateVideoDecoderOutputView;

HRESULT APIENTRY* CreateVideoDecoderOutputView(
  _In_       D3D10DDI_HDEVICE                           hDevice,
  _In_ const D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW *pCreateData,
  _In_       D3D11_1DDI_HVIDEODECODEROUTPUTVIEW         hView,
  _In_       D3D11_1DDI_HRTVIDEODECODEROUTPUTVIEW       hRTView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *


### -param D3D11_1DDI_HVIDEODECODEROUTPUTVIEW


### -param D3D11_1DDI_HRTVIDEODECODEROUTPUTVIEW








#### - hDevice [in]

A handle to the display device (graphics context).




#### - hRTView [in]

A handle to the video decoder output view that the driver should use when it calls back into the Direct3D runtime.


#### - hView [in]

A handle to the driver's private data for the video decoder output view. For more information, see the Remarks section.


#### - pCreateData [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoderoutputview.md">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a> structure. This structure specifies the attributes of the video decoder output view to be created.


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



The Direct3D runtime calls <i>CreateVideoDecoderOutputView</i> after it has called the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize.md">CalcPrivateVideoProcessorOutputViewSize</a>  to determine the size in bytes for the private data that the driver requires for the video decoder object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video decoder object.

When the runtime  calls <i>CreateVideoDecoderOutputView</i>, it passes the handle to the private data memory in the <i>hView</i> parameter. This handle is actually  a pointer to the memory. 




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder.md">D3D11_1DDIARG_CREATEVIDEODECODER</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize.md">CalcPrivateVideoProcessorOutputViewSize</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe.md">VideoDecoderBeginFrame</a>



 

 


