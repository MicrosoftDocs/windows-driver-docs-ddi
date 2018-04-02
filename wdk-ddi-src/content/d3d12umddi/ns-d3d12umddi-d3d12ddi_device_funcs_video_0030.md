---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0030
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0030
author: windows-driver-content
description: Video device functions.
old-location: display\d3d12ddi-device-funcs-video-0030.htm
old-project: display
ms.assetid: 39647e7d-d89f-43f4-916a-cbfa5ba28611
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_DEVICE_FUNCS_VIDEO_0030, D3D12DDI_DEVICE_FUNCS_VIDEO_0030 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO_0030, display.d3d12ddi-device-funcs-video-0030
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_DEVICE_FUNCS_VIDEO_0030
product: Windows
targetos: Windows
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

