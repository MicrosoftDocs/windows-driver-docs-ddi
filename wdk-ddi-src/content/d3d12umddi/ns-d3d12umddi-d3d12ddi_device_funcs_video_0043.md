---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0043
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0043
description: The device functions of video.
ms.assetid: fe5212da-f9de-493f-a4ab-844d8bcb7bc9
ms.date: 10/19/2018
ms.topic: struct
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
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_DEVICE_FUNCS_VIDEO_0043
product: 
- Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_DEVICE_FUNCS_VIDEO_0043 structure

## -description

The device functions of video.


## -syntax


```cpp
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
```


## -struct-fields




### -field pfnGetCaps

Get capabilities. See [PFND3D12DDI_VIDEO_GETCAPS](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md).


### -field pfnCalcPrivateVideoDecoderSize

Calculates the private video decoder size. See [PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0032](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideodecodersize_0032.md).


### -field pfnCreateVideoDecoder

Creates a video decoder. See [PFND3D12DDI_CREATEVIDEODECODER_0032](nc-d3d12umddi-pfnd3d12ddi_createvideodecoder_0032.md).


### -field pfnDestroyVideoDecoder

Destroys the video decoder. See [PFND3D12DDI_DESTROYVIDEODECODER_0021](nc-d3d12umddi-pfnd3d12ddi_destroyvideodecoder_0021.md).


### -field pfnCalcPrivateVideoDecoderHeapSize

Calculates the private video decoder heap size. See [PFND3D12DDI_CALCPRIVATEVIDEODECODERHEAPSIZE_0033](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideodecoderheapsize_0033.md).


### -field pfnCreateVideoDecoderHeap

Creates the video decoder heap. See [PFND3D12DDI_CREATEVIDEODECODERHEAP_0033](nc-d3d12umddi-pfnd3d12ddi_createvideodecoderheap_0033.md).


### -field pfnDestroyVideoDecoderHeap

Destroys the video decoder heap. See [PFND3D12DDI_DESTROYVIDEODECODERHEAP_0032](nc-d3d12umddi-pfnd3d12ddi_destroyvideodecoderheap_0032.md).


### -field pfnCalcPrivateVideoProcessorSize

Calculates the private video processor size. See [PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoprocessorsize_0043.md).


### -field pfnCreateVideoProcessor

Creates the video processor. See [PFND3D12DDI_CREATEVIDEOPROCESSOR_0032](nc-d3d12umddi-pfnd3d12ddi_createvideoprocessor_0043.md).


### -field pfnDestroyVideoProcessor

Destroys the video processor. See [PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021](nc-d3d12umddi-pfnd3d12ddi_destroyvideoprocessor_0021.md).


