---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_0080
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_0080 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_0080
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_0080
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_0080
---

## -description

The **D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_0080** structure specifies the parameters for the intra-refresh mode that should be used when triggering intra-refresh sessions.

## -struct-fields

### -field Mode

A [**D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_MODE_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_intra_refresh_mode_0080.md) value that indicates the type of intra refresh to be used.

### -field IntraRefreshDuration

The duration of the intra-refresh session, in number of frames. If **Mode** is **D3D12DDI_VIDEO_ENCODER_INTRA_REFRESH_MODE_ROW_BASED_0080**, **IntraRefreshDuration** and the frame height define the size of the I rows for the duration of the IR session.

## -remarks

When triggering an intra-refresh session, the host informs the current frame number relative to the [0..**IntraRefreshDuration**) session by setting **IntraRefreshFrameIndex** in the [picture control structure](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_desc_0082_0.md
).

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_DESC_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_desc_0082_0.md
)

[**D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_control_desc_0082_0.md)

[**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md)
