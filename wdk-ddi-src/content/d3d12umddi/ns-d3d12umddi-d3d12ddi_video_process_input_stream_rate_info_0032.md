---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032
title: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032 (d3d12umddi.h)
description: The video process input stream rate info.
old-location: display\d3d12ddi-video-process-input-stream-rate-info-0032.htm
ms.assetid: 4ca68dac-ead1-431e-a97e-af99ef966417
ms.date: 04/16/2018
keywords: ["D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032 structure"]
ms.keywords: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032, display.d3d12ddi-video-process-input-stream-rate-info-0032
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032"
 - "D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d12umddi.h
api_name:
- D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032
---

# D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032 structure


## -description


The video process input stream rate info.


## -struct-fields




### -field OutputIndex

The OutputIndex member is a zero-based cyclic number that indicates the frame index number of the output frame. The driver uses this output-index information to perform the video processing in a certain pattern or cycle, especially when the driver performs deinterlacing or frame-rate conversion.With the following output-index pattern, the driver performs the indicated video processing:

* Progressive format at normal and half rate:  OutputIndex = 0, 0, ...
* Progressive format at 2/1 custom rate (double frame-rate conversion, OutputFrames=2):  OutputIndex = 0, 1, 0, 1, ...
* Interlaced format at normal rate:  OutputIndex = 0, 1, 0, 1, ... (0: first field, 1: second field)
* Interlaced format at half rate: OutputIndex = 0, 0, ... (for example, first and second fields are blended into one frame)
* Interlaced at 4/5 custom rate (3:2 inverse telecine, OutputFrames=4):  OutputIndex = 0, 1, 2, 3, 0, 1, 2, 3,... (0:A, 1:B, 2:C, 3:D film frame)

### -field InputFrameOrField

The InputFrameOrField member is a zero-based number that indicates the frame or the field number of the input surface. With the following input-frame-or-field number, the driver can perform the indicated video processing:

* Progressive format and interlaced format at normal rate: InputFrameOrField = 0, 1, 2, ...
* Progressive format and interlaced format at half rate: InputFrameOrField = 0, 2, 4, ...
* Interlaced format at 4/5 custom rate (3:2 inverse telecine, OutputFrames=4 and InputFrameOrField=10):  InputFrameOrField = 0, 0, 0, 0, 10, 10, 10, 10, 20, 20, 20, 20, ...
* Interlaced format at 4/15 custom rate (8:7 inverse telecine, OutputFrames=2 and InputFrameOrField=15): InputFrameOrField = 0, 0, 15, 15, 30, 30, ...


