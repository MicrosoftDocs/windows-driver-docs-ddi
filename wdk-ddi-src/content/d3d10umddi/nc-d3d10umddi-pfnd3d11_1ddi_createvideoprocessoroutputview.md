---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEOPROCESSOROUTPUTVIEW
title: PFND3D11_1DDI_CREATEVIDEOPROCESSOROUTPUTVIEW (d3d10umddi.h)
description: Creates a resource view for a video processor. This view defines the output sample for the video processing operation.
old-location: display\createvideoprocessoroutputview.htm
ms.assetid: 619695dc-8525-4200-a0c2-8ce0fb1010ed
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_CREATEVIDEOPROCESSOROUTPUTVIEW callback function"]
ms.keywords: CreateVideoProcessorOutputView, CreateVideoProcessorOutputView callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEOPROCESSOROUTPUTVIEW, PFND3D11_1DDI_CREATEVIDEOPROCESSOROUTPUTVIEW callback, d3d10umddi/CreateVideoProcessorOutputView, display.createvideoprocessoroutputview
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
 - "d3d10umddi/CreateVideoProcessorOutputView"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CreateVideoProcessorOutputView
product:
 - Windows
---

# PFND3D11_1DDI_CREATEVIDEOPROCESSOROUTPUTVIEW callback function

## -description

Creates a resource view for a video processor. This view defines the output sample for the video processing operation.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideoprocessoroutputview">D3D11_1DDIARG_CREATEVIDEOPROCESSOROUTPUTVIEW</a> structure. This structure specifies the attributes of the video processor output view to be created.

### -param Arg3

*hView* [in]

A handle to the driver's private data for the video processor output view.

### -param Arg4

*hRTView* [in]

A handle to the video processor output view that the driver should use when it calls back into the Direct3D runtime.

## -returns

<i>CreateVideoProcessorOutputView</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The video processor input view was created successfully.|
|D3DDDIERR_DEVICEREMOVED|The graphics adapter was removed.|
|DXGI_ERROR_UNSUPPORTED|The D3D11_1DDIARG_CREATEVIDEOPROCESSORINPUTVIEW contained incorrect or unsupported data. For example, the driver should return DXGI_ERROR_UNSUPPORTED if the FourCC member specified an unsupported code value.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -remarks

The Direct3D runtime calls <i>CreateVideoProcessorOutputView</i> after it has called the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize">CalcPrivateVideoProcessorOutputViewSize</a>   to determine the size in bytes for the private data that the driver requires for the video processor output view. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video processor output view.

When the runtime  calls <i>CreateVideoProcessorOutputView</i>, it passes the handle to the private data memory in the <i>hView</i> parameter. This handle is actually a pointer to the memory.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize">CalcPrivateVideoProcessorOutputViewSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideodecoderoutputview">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a>

