---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAGS_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAGS_0082_0
ms.date: 02/02/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAGS_0082_0 enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAGS_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAGS_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAGS_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAGS_0082_0** enumeration defines the set of flags for the sequence control properties.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAG_0082_0_NONE

No flags.

### -field D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAG_0082_0_RESOLUTION_CHANGE

Indicates a change in [**D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC_0082_0.PictureTargetResolution**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_control_desc_0082_0.md).

### -field D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAG_0082_0_RATE_CONTROL_CHANGE

Indicates a change in [**D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC_0082_0.RateControl**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_control_desc_0082_0.md).

### -field D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAG_0082_0_SUBREGION_LAYOUT_CHANGE

Indicates a change in [**D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC_0082_0.SelectedLayoutMode**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_control_desc_0082_0.md) or **FrameSubregionsLayoutData**.

### -field D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAG_0082_0_REQUEST_INTRA_REFRESH

Starts an intra-refresh session starting at this frame using the configuration in  [**D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC_0082_0.IntraRefreshConfig**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_control_desc_0082_0.md).

### -field D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_FLAG_0082_0_GOP_SEQUENCE_CHANGE

Indicates a change in [**D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC_0082_0.CodecGopSequence**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_control_desc_0082_0.md).

## -remarks

Depending on the codec, a request for reconfiguration might need to insert an IDR in the bitstream and new SPS headers.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_control_desc_0082_0.md)
