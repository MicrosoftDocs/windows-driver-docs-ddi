---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020
title: D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020 (d3d12umddi.h)
description: Specifies information used to retrieve the maximum number of input data streams that can be enabled for a video processor.
old-location: display\d3d12ddi_video_process_max_input_streams_data.htm
ms.assetid: 41518F04-4AD1-4057-8988-5934F3875B8E
ms.date: 04/16/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020, D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020, display.d3d12ddi_video_process_max_input_streams_data
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020"
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
- D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020
---

# D3D12DDI_VIDEO_PROCESS_MAX_INPUT_STREAMS_DATA_0020 structure


## -description


Specifies information used to retrieve the maximum number of input data streams that can be enabled for a video processor.
This structure is used in the D3D12DDICAPS_TYPE_VIDEO_PROCESS_MAX_INPUT_STREAMS capabilities check as part of [D3D12DDICAPS_TYPE_VIDEO_0020](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md).

## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field MaxInputStreams

The maximum number of streams that can be enabled for the video processor at the same time.

