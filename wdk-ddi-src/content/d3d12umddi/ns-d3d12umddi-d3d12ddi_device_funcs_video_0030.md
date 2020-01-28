---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0030
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0030 (d3d12umddi.h)
description: Video device functions.
old-location: display\d3d12ddi-device-funcs-video-0030.htm
ms.assetid: 39647e7d-d89f-43f4-916a-cbfa5ba28611
ms.date: 05/10/2018
ms.keywords: D3D12DDI_DEVICE_FUNCS_VIDEO_0030, D3D12DDI_DEVICE_FUNCS_VIDEO_0030 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO_0030, display.d3d12ddi-device-funcs-video-0030
f1_keywords:
 - "d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO_0030"
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
req.max-support: Windows 10, version 1709
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d12umddi.h
api_name:
- D3D12DDI_DEVICE_FUNCS_VIDEO_0030
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_DEVICE_FUNCS_VIDEO_0030
---

# D3D12DDI_DEVICE_FUNCS_VIDEO_0030 structure


## -description


Video device functions.


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

