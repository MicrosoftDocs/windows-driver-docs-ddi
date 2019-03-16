---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_DECODE_STATUS_0020
title: D3D12DDI_VIDEO_DECODE_STATUS_0020 (d3d12umddi.h)
description: Contains status values for video decode.
old-location: display\d3d12ddi_video_decode_status.htm
ms.assetid: E7A3944D-142E-450C-B9EE-9190BF264C60
ms.date: 04/16/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_STATUS_0020, D3D12DDI_VIDEO_DECODE_STATUS_0020 enumeration [Display Devices], D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE, D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE_SKIP_DISPLAY, D3D12DDI_VIDEO_DECODE_STATUS_0020_OK, D3D12DDI_VIDEO_DECODE_STATUS_0020_RATE_EXCEEDED, D3D12DDI_VIDEO_DECODE_STATUS_0020_RESTART, d3d12umddi/D3D12DDI_VIDEO_DECODE_STATUS_0020, d3d12umddi/D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE, d3d12umddi/D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE_SKIP_DISPLAY, d3d12umddi/D3D12DDI_VIDEO_DECODE_STATUS_0020_OK, d3d12umddi/D3D12DDI_VIDEO_DECODE_STATUS_0020_RATE_EXCEEDED, d3d12umddi/D3D12DDI_VIDEO_DECODE_STATUS_0020_RESTART, display.d3d12ddi_video_decode_status
ms.topic: enum
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
- D3D12DDI_VIDEO_DECODE_STATUS_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODE_STATUS_0020
---

# D3D12DDI_VIDEO_DECODE_STATUS_0020 enumeration


## -description


Contains status values for video decode.


## -enum-fields




### -field D3D12DDI_VIDEO_DECODE_STATUS_0020_OK

Operation succeeded.


### -field D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE

There was a minor problem in the data format, but the host decoder should continue processing.


### -field D3D12DDI_VIDEO_DECODE_STATUS_0020_CONTINUE_SKIP_DISPLAY

There was a significant problem in the data format. The host decoder should continue processing, but should skip display.


### -field D3D12DDI_VIDEO_DECODE_STATUS_0020_RESTART

There was a severe problem in the data format. The host decoder should restart the entire decoding process, starting at a sequence or random-access entry point.


### -field D3D12DDI_VIDEO_DECODE_STATUS_0020_RATE_EXCEEDED

The bit rate or frame rate supplied to decode stream creation was insufficient for this frame.  When this status is reported, the <b>BitRate</b> member of the [D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS](ns-d3d12umddi-d3d12ddi_query_data_video_decode_statistics_0022.md) structure reports a value that can be used to recreate the decode stream at the same frame rate and succeed decoding the failed frames.  Subsequent frames may still fail if those frames exceed the new value.  The reported bit rate is calculated with the frame rate with which the stream was created.


## -see-also




[D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS](ns-d3d12umddi-d3d12ddi_query_data_video_decode_statistics_0022.md)
 

 

