---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0030
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0030
author: windows-driver-content
description: Video device functions.
old-location: display\d3d12ddi-device-funcs-video-0030.htm
old-project: display
ms.assetid: 39647e7d-d89f-43f4-916a-cbfa5ba28611
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO_0030, D3D12DDI_DEVICE_FUNCS_VIDEO_0030 structure [Display Devices], display.d3d12ddi-device-funcs-video-0030, D3D12DDI_DEVICE_FUNCS_VIDEO_0030
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d12umddi.h
apiname:
-	D3D12DDI_DEVICE_FUNCS_VIDEO_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_DEVICE_FUNCS_VIDEO_0030
---

# D3D12DDI_DEVICE_FUNCS_VIDEO_0030 structure


## -description


Video device functions.


## -syntax


````
typedef struct _D3D12DDI_DEVICE_FUNCS_VIDEO_0030 {
  PFND3D12DDI_VIDEO_GETCAPS                                     pfnGetCaps;
  PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021                  pfnCalcPrivateVideoDecoderSize;
  PFND3D12DDI_CREATEVIDEODECODER_0021                           pfnCreateVideoDecoder;
  PFND3D12DDI_DESTROYVIDEODECODER_0021                          pfnDestroyVideoDecoder;
  PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0021                pfnCalcPrivateVideoProcessorSize;
  PFND3D12DDI_CREATEVIDEOPROCESSOR_0021                         pfnCreateVideoProcessor;
  PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021                        pfnDestroyVideoProcessor;
  PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020               pfnGetDecodeProfileCount;
  PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020                pfnGetDecodeFormatCount;
  PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020  pfnGetBitstreamEncryptionSchemeCount;
  PFND3D12DDI_VIDEO_DECODER_TRIM_ALLOCATIONS_0021               pfnDecoderTrimAllocations;
  PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021             pfnProcessorTrimAllocations;
} D3D12DDI_DEVICE_FUNCS_VIDEO_0030, D3D12DDI_DEVICE_FUNCS_VIDEO_0030;
````


## -struct-fields




### -field pfnGetCaps

Get caps.


### -field pfnCalcPrivateVideoDecoderSize

Calculate private video decoder size.


### -field pfnCreateVideoDecoder

Create video decoder.


### -field pfnDestroyVideoDecoder

Destroy video decoder.


### -field pfnCalcPrivateVideoProcessorSize

Calculate private video processor size.


### -field pfnCreateVideoProcessor

Create video processor.


### -field pfnDestroyVideoProcessor

Destroy video processor.


### -field pfnGetDecodeProfileCount

Get decode profile count.


### -field pfnGetDecodeFormatCount

Get decode format count.


### -field pfnGetBitstreamEncryptionSchemeCount

Get bitstream encryption scheme count.


### -field pfnDecoderTrimAllocations

Decoder trim allocations.


### -field pfnProcessorTrimAllocations

Processor trim allocations.

