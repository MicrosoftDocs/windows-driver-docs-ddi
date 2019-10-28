---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW
title: PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW (d3d10umddi.h)
description: Creates a resource view for a video decoder. This view defines the output sample for the video decoding operation.
old-location: display\createvideodecoderoutputview.htm
ms.assetid: a5a32b4e-799c-4d18-995d-f804e6dff85c
ms.date: 05/10/2018
ms.keywords: CreateVideoDecoderOutputView, CreateVideoDecoderOutputView callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW, PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW callback, d3d10umddi/CreateVideoDecoderOutputView, display.createvideodecoderoutputview
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/CreateVideoDecoderOutputView"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CreateVideoDecoderOutputView
product:
 - Windows
---

# PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW callback function

## -description

Creates a resource view for a video decoder. This view defines the output sample for the video decoding operation.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideodecoderoutputview">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a> structure. This structure specifies the attributes of the video decoder output view to be created.

### -param Arg3

*hRTView* [in]

A handle to the video decoder output view that the driver should use when it calls back into the Direct3D runtime.

### -param Arg4

## -returns

<b>CreateVideoDecoderOutputView</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The video decoder output view was created successfully. | 
| **D3DDDIERR_DEVICEREMOVED** | The graphics adapter was removed. | 
| **E_OUTOFMEMORY** |     Memory was not available to complete the operation. |

## -remarks

The Direct3D runtime calls <i>CreateVideoDecoderOutputView</i> after it has called the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize">CalcPrivateVideoProcessorOutputViewSize</a>  to determine the size in bytes for the private data that the driver requires for the video decoder object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video decoder object.

When the runtime  calls <i>CreateVideoDecoderOutputView</i>, it passes the handle to the private data memory in the <i>hView</i> parameter. This handle is actually  a pointer to the memory.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize">CalcPrivateVideoProcessorOutputViewSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder">D3D11_1DDIARG_CREATEVIDEODECODER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange">NegotiateCryptoSessionKeyExchange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe">VideoDecoderBeginFrame</a>

