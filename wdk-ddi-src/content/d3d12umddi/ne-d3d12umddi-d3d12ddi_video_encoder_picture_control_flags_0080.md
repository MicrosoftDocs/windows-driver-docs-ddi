---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_FLAGS_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_FLAGS_0080
ms.date: 02/02/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_FLAGS_0080 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_FLAGS_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_FLAGS_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_FLAGS_0080
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_FLAGS_0080
---

## -description

The **D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_FLAGS_0080** enumeration defines the set of flags for picture control properties.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_FLAG_0080_NONE

No flags.

### -field D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_FLAG_0080_USED_AS_REFERENCE_PICTURE

When set, indicates that this frame will be used as a reference frame in future encode commands. This value also indicates to output the reconstructed picture along with the bistream for the host to place it, in future calls, in the reconstructed pictures reference list. Check feature support before setting this flag because there might be limitations for some frame types to be marked as references.

> [!NOTE]
>
> If this flag is not set, **pReconstructedPicture** can be a NULL pointer on the [**EncodeFrame**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) call.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_DESC_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_desc_0082_0.md)

[**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md)
