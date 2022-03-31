---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_REFERENCE_PICTURE_DESCRIPTOR_HEVC_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_REFERENCE_PICTURE_DESCRIPTOR_HEVC_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_REFERENCE_PICTURE_DESCRIPTOR_HEVC_0082_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_REFERENCE_PICTURE_DESCRIPTOR_HEVC_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_REFERENCE_PICTURE_DESCRIPTOR_HEVC_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_REFERENCE_PICTURE_DESCRIPTOR_HEVC_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_REFERENCE_PICTURE_DESCRIPTOR_HEVC_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_REFERENCE_PICTURE_DESCRIPTOR_HEVC_0082_0** structure represents a reference picture descriptor for HEVC video encoding.

## -struct-fields

### -field ReconstructedPictureResourceIndex

Maps the current reference picture described by this structure to a resource in the [**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_DESC_0082_0.ReferenceFrames**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_desc_0082_0.md) array.

### -field IsRefUsedByCurrentPic

Set when this descriptor entry is being used by the current picture by being indexed from the L0 and/or L1 lists.

### -field IsLongTermReference

Set when the described reference frame is being used as a long-term reference picture.

### -field PictureOrderCountNumber

Indicates the described reference frame display order.

### -field TemporalLayerIndex

Picture layer number in temporal hierarchy. Check [**D3D12DDI_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT_H264_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_codec_configuration_support_h264_0082_0.md) for the maximum number of layers.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_HEVC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_codec_data_hevc_0082_0.md)
