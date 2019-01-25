---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0033
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0033 (d3d12umddi.h)
description: The device functions of video.
old-location: display\d3d12ddi-device-funcs-video-0033.htm
ms.assetid: faaaf6e5-9f4d-4051-a656-92c1394cda24
ms.date: 04/16/2018
ms.keywords: D3D12DDI_DEVICE_FUNCS_VIDEO_0033, D3D12DDI_DEVICE_FUNCS_VIDEO_0033 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO_0033, display.d3d12ddi-device-funcs-video-0033
ms.topic: struct
req.header: d3d12umddi.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
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
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_DEVICE_FUNCS_VIDEO_0033
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_DEVICE_FUNCS_VIDEO_0033
---

# D3D12DDI_DEVICE_FUNCS_VIDEO_0033 structure


## -description


The device functions of video.


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

Calculates the private video processor size. See [PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032](nc-d3d12umddi-pfnd3d12ddi_calcprivatevideoprocessorsize_0032.md).


### -field pfnCreateVideoProcessor

Creates the video processor. See [PFND3D12DDI_CREATEVIDEOPROCESSOR_0032](nc-d3d12umddi-pfnd3d12ddi_createvideoprocessor_0032.md).


### -field pfnDestroyVideoProcessor

Destroys the video processor. See [PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021](nc-d3d12umddi-pfnd3d12ddi_destroyvideoprocessor_0021.md).

