---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW
title: PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW
author: windows-driver-content
description: Creates a resource view for a video processor. This view defines the input sample for the video processing operation.
old-location: display\createvideoprocessorinputview.htm
old-project: display
ms.assetid: f3942c53-e366-41c5-9f43-d093fa6b6ed6
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CreateVideoProcessorInputView, CreateVideoProcessorInputView callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW, PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW callback, d3d10umddi/CreateVideoProcessorInputView, display.createvideoprocessorinputview
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
-	CreateVideoProcessorInputView
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW callback function


## -description


Creates a resource view for a video processor. This view defines the input sample for the video processing operation.


## -parameters




### -param Arg1


### -param *


### -param Arg2


### -param Arg3








#### - hDevice [in]

A handle to the display device (graphics context).




#### - hRTView [in]

A handle to the video processor input that the driver should use when it calls back into the Direct3D runtime.


#### - hView [in]

A handle to the driver's private data for the video processor input view. For more information, see the Remarks section.


#### - pView [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406318">D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW</a> structure. This structure specifies the attributes of the video processor input view to be created.


## -returns



<b>CreateVideoProcessorInputView</b> returns one of the following values:

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
The video processor input view was created successfully.

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
<dt><b>DXGI_ERROR_UNSUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW contained incorrect or unsupported data. For example, the driver should return <b>DXGI_ERROR_UNSUPPORTED</b> if the <b>FourCC</b> member specified an unsupported code value.

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



The Direct3D runtime calls <i>CreateVideoProcessorInputView</i> after it has called the driver's <a href="https://msdn.microsoft.com/3cdf467c-41f5-4a44-b10a-41aeb76ca815">CalcPrivateVideoProcessorInputViewSize</a>   to determine the size in bytes for the private data that the driver requires for the video processor input view. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video processor input view.

When the runtime  calls <i>CreateVideoProcessorInputView</i>, it passes the handle to the private data memory in the <i>hView</i> parameter. This handle is actually a pointer to the memory. 




## -see-also




<a href="https://msdn.microsoft.com/3cdf467c-41f5-4a44-b10a-41aeb76ca815">CalcPrivateVideoProcessorInputViewSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406318">D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW</a>
 

 

