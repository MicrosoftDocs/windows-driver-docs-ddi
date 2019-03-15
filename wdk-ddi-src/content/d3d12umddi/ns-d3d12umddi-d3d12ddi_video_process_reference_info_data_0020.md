---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020
title: D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020 (d3d12umddi.h)
description: Data structure for D3D12DDICAPS_VIDEO_PROCESS_REFERENCE_INFO capability check. Retrieves the number of past and future frames required for a given deinterlace mode.
old-location: display\d3d12ddi_video_process_reference_info_data.htm
ms.assetid: 3711ACBD-482E-4BB8-8530-C92DA610CA5B
ms.date: 04/16/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020, D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020, display.d3d12ddi_video_process_reference_info_data
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020
---

# D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020 structure


## -description


Retrieves the number of past and future frames required for a given deinterlace mode. This structure is for the D3D12DDICAPS_VIDEO_PROCESS_REFERENCE_INFO capability check in [D3D12DDICAPS_TYPE_VIDEO_0020](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md).


## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field DeinterlaceMode

The deinterlacing mode for which to retrieve the number of past and future frames. Only a single mode may be queried at once. See the [D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS](ne-d3d12umddi-d3d12ddi_video_process_deinterlace_flags_0020.md) enumeration for a list of modes.


### -field Filters

The filters for which to retrieve the number of past and future frames. Multiple filters may be specified. For more information, see the [D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS](ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020.md) enumeration.


### -field FeatureSupport

The features for which to retrieve the number of past and future frames. For more information, see the [D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS](ne-d3d12umddi-d3d12ddi_video_process_feature_support_flags_0020.md) enumeration.


### -field InputFrameRate

The input rate of the stream.


### -field OutputFrameRate

The output rate of the stream.


### -field EnableAutoProcessing

Whether automatic processing is used. TRUE if auto processing is used.


### -field PastFrames

The number of past reference frames required to support this processing.


### -field FutureFrames

The number of future reference frames required to support this processing.



## -see-also




[D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS](ne-d3d12umddi-d3d12ddi_video_process_deinterlace_flags_0020.md)



[D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS](ne-d3d12umddi-d3d12ddi_video_process_feature_support_flags_0020.md)



[D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS](ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020.md)
 

 

