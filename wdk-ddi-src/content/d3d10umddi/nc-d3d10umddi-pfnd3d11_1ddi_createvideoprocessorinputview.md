---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW
title: PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW (d3d10umddi.h)
description: Creates a resource view for a video processor. This view defines the input sample for the video processing operation.
old-location: display\createvideoprocessorinputview.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW callback function"]
ms.keywords: CreateVideoProcessorInputView, CreateVideoProcessorInputView callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW, PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW callback, d3d10umddi/CreateVideoProcessorInputView, display.createvideoprocessorinputview
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW
 - d3d10umddi/PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CreateVideoProcessorInputView
product:
 - Windows
---

# PFND3D11_1DDI_CREATEVIDEOPROCESSORINPUTVIEW callback function


## -description

Creates a resource view for a video processor. This view defines the input sample for the video processing operation.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pView* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessorinputview">D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW</a> structure. This structure specifies the attributes of the video processor input view to be created.

### -param Arg3

*hView* [in]

A handle to the driver's private data for the video processor input.

### -param Arg4

*hRTView* [in]

A handle to the video processor input that the driver should use when it calls back into the Direct3D runtime.

## -returns

<b>CreateVideoProcessorInputView</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The video processor input view was created successfully.|
|D3DDDIERR_DEVICEREMOVED|The graphics adapter was removed.|
|DXGI_ERROR_UNSUPPORTED|The D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW contained incorrect or unsupported data. For example, the driver should return DXGI_ERROR_UNSUPPORTED if the FourCC member specified an unsupported code value.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -remarks

The Direct3D runtime calls <i>CreateVideoProcessorInputView</i> after it has called the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorinputviewsize">CalcPrivateVideoProcessorInputViewSize</a>   to determine the size in bytes for the private data that the driver requires for the video processor input view. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video processor input view.

When the runtime  calls <i>CreateVideoProcessorInputView</i>, it passes the handle to the private data memory in the <i>hView</i> parameter. This handle is actually a pointer to the memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessorinputviewsize">CalcPrivateVideoProcessorInputViewSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessorinputview">D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW</a>
