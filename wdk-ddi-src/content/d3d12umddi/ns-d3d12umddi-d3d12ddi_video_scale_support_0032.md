---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_SCALE_SUPPORT_0032
title: D3D12DDI_VIDEO_SCALE_SUPPORT_0032 (d3d12umddi.h)
description: Video scale support.
old-location: display\d3d12ddi-video-scale-support-0032.htm
ms.date: 04/16/2018
keywords: ["D3D12DDI_VIDEO_SCALE_SUPPORT_0032 structure"]
ms.keywords: D3D12DDI_VIDEO_SCALE_SUPPORT_0032, D3D12DDI_VIDEO_SCALE_SUPPORT_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_0032, display.d3d12ddi-video-scale-support-0032
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
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_SCALE_SUPPORT_0032
f1_keywords:
 - D3D12DDI_VIDEO_SCALE_SUPPORT_0032
 - d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_0032
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_SCALE_SUPPORT_0032
---

# D3D12DDI_VIDEO_SCALE_SUPPORT_0032 structure

## -description

The **D3D12DDI_VIDEO_SCALE_SUPPORT_0032** structure describes a supported range of output sizes for a scaler.

## -struct-fields

### -field OutputSizeRange

A [**D3D12DDI_VIDEO_SIZE_RANGE_0032**](ns-d3d12umddi-d3d12ddi_video_size_range_0032.md) structure that specifies the supported range of output sizes for a scaler.

### -field Flags

A [**D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022**](ne-d3d12umddi-d3d12ddi_video_scale_support_flags_0022.md) value that indicated level of scale support.

## -remarks

By default, the supported range indicates all possible output size combinations that exist between the Max size and Min size for the extent, ScaleSupportFlags may add additional caveats.

When scaling is not supported, the Min and Max sizes should both be set to the input size and no flags specified.

## -see-also

[**D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032**](ns-d3d12umddi-d3d12ddi_video_process_support_data_0032.md)

[**D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032**](ns-d3d12umddi-d3d12ddi_video_process_support_data_0032.md)

[**D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022**](ne-d3d12umddi-d3d12ddi_video_scale_support_flags_0022.md)

[**D3D12DDI_VIDEO_SIZE_RANGE_0032**](ns-d3d12umddi-d3d12ddi_video_size_range_0032.md)
