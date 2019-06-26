---
UID: NS:d3d12umddi.D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022
title: D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022 (d3d12umddi.h)
description: Video decode statistics for a query.
old-location: display\d3d12ddi_query_data_video_decode_statistics.htm
ms.assetid: F58AB9E1-4061-46B8-8137-319DF30D9CA7
ms.date: 04/16/2018
ms.keywords: D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022, D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022 structure [Display Devices], d3d12umddi/D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022, display.d3d12ddi_query_data_video_decode_statistics
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
- D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022
---

# D3D12DDI_QUERY_DATA_VIDEO_DECODE_STATISTICS_0022 structure


## -description


Video decode statistics for a query.


## -struct-fields




### -field Status

Specifies the status of an operation as a [D3D12DDI_VIDEO_DECODE_STATUS](ne-d3d12umddi-d3d12ddi_video_decode_status_0020.md) value. This value is extended to 64bits to accommodate predication.


### -field NumMacroblocksAffected

The number of blocks affected. If the <b>Status</b> value is not 0, this member contains an estimate from the accelerator of the number of super-blocks in the decoded frame that were adversely affected by the reported problem. If the accelerator does not provide an estimate, the value is `0xFFFFFFFFFFFFFFFF`.


### -field FrameRate

The frame rate.

### -field BitRate

When the <b>Status</b> value returned is <b>D3D12DDI_VIDEO_DECODE_STATUS_RATE_EXCEEDED</b>, this member reports the required bit rate.  This value may be used to recreate the decode stream and try again.  The updated value is relative to the frame rate with which the stream was created.  A value of zero (0) is valid to indicate that the worst case bit rate should be assumed.
For all other <b>Status</b> values, <b>BitRate</b> is not used and is set to zero.



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_status_0020">D3D12DDI_VIDEO_DECODE_STATUS</a>
 

 

