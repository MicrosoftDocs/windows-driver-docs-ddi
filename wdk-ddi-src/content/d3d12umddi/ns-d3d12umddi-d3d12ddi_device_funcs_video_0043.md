---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0043
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0043
author: windows-driver-content
description:
ms.assetid: fe5212da-f9de-493f-a4ab-844d8bcb7bc9
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDI_DEVICE_FUNCS_VIDEO_0043, D3D12DDI_DEVICE_FUNCS_VIDEO_0043,
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_DEVICE_FUNCS_VIDEO_0043
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3d12umddi.h
apiname:
-	D3D12DDI_DEVICE_FUNCS_VIDEO_0043
product: Windows
targetos: Windows
---

# D3D12DDI_DEVICE_FUNCS_VIDEO_0043 structure

## -description

The device functions of video.


## -syntax


````
typedef struct D3D12DDI_DEVICE_FUNCS_VIDEO_0043
{
    PFND3D12DDI_VIDEO_GETCAPS                                           pfnGetCaps;
    PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0032                        pfnCalcPrivateVideoDecoderSize;
    PFND3D12DDI_CREATEVIDEODECODER_0032                                 pfnCreateVideoDecoder;
    PFND3D12DDI_DESTROYVIDEODECODER_0021                                pfnDestroyVideoDecoder;
    PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033                    pfnCalcPrivateVideoDecoderHeapSize;
    PFND3D12DDI_CREATEVIDEODECODERHEAP_0033                             pfnCreateVideoDecoderHeap;
    PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032                            pfnDestroyVideoDecoderHeap;
    PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043                      pfnCalcPrivateVideoProcessorSize;
    PFND3D12DDI_CREATEVIDEOPROCESSOR_0043                               pfnCreateVideoProcessor;
    PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021                              pfnDestroyVideoProcessor;
} D3D12DDI_DEVICE_FUNCS_VIDEO_0043;
````


## -struct-fields




### -field pfnGetCaps

Get caps.


### -field pfnCalcPrivateVideoDecoderSize

Calculates the private video decoder size.


### -field pfnCreateVideoDecoder

Creates a video decoder.


### -field pfnDestroyVideoDecoder

Destroys the video decoder.


### -field pfnCalcPrivateVideoDecoderHeapSize

Calculates the private video decoder heap size.


### -field pfnCreateVideoDecoderHeap

Creates the video decoder heap.


### -field pfnDestroyVideoDecoderHeap

Destroys the video decoder heap.


### -field pfnCalcPrivateVideoProcessorSize

Calculates the private video processor size.


### -field pfnCreateVideoProcessor

Creates the video processor.


### -field pfnDestroyVideoProcessor

Destroys the video processor.

