---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_MARKING_OPERATION_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_MARKING_OPERATION_0082_0
ms.date: 02/02/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_MARKING_OPERATION_0082_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_MARKING_OPERATION_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_MARKING_OPERATION_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_MARKING_OPERATION_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_MARKING_OPERATION_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_MARKING_OPERATION_0082_0** structure describes changes in the reference pictures as memory operations as a tuple of an operation identifier and associated parameters needed for the operation.

## -struct-fields

### -field memory_management_control_operation

The control operation to be applied to affect the reference picture marking state. Valid operation values follow.

| Value | Description |
| ----- | ----------- |
|  0    | End memory_management_control_operation syntax element loop. |
|  1    | Mark a short-term reference picture as "unused for reference". |
|  2    | Mark a long-term reference picture as "unused for reference". |
|  3    | Mark a short-term reference picture as "used for long-term reference" and assign a long-term frame index to it. |
|  4    | Specify the maximum long-term frame index and mark all long-term reference pictures having long-term frame indices greater than the maximum value as "unused for reference". |
|  5    | Mark all reference pictures as "unused for reference" and set the *MaxLongTermFrameIdx* variable to "no long-term frame indices". |
|  6    | Mark the current picture as "used for long-term reference" and assign a long-term frame index to it. |

### -field difference_of_pic_nums_minus1

This member is used with **memory_management_control_operation** equal to 3 or 1 to assign a long-term frame index to a short-term reference picture or to mark a short-term reference picture as "unused for reference". When the associated **memory_management_control_operation** is processed by the decoding process, the resulting picture number derived from **difference_of_pic_nums_minus1** shall be a picture number assigned to one of the reference pictures marked as "used for reference" and not previously assigned to a long-term frame index.

### -field long_term_pic_num

This member is used with **memory_management_control_operation** equal to 2 to mark a long-term reference picture as "unused for reference". When the associated **memory_management_control_operation** is processed by the decoding process, **long_term_pic_num** shall be equal to a long-term picture number assigned to one of the reference pictures that is currently marked as "used for long-term reference".

### -field long_term_frame_idx

This member is used with **memory_management_control_operation** equal to 3 or 6 to assign a long-term frame index to a picture. When the associated **memory_management_control_operation** is processed by the decoding process, the value of **long_term_frame_idx** shall be in the range of 0 to *MaxLongTermFrameIdx*, inclusive.

### -field max_long_term_frame_idx_plus1

The value minus 1 specifies the maximum value of long-term frame index allowed for long-term reference pictures (until receipt of another value of **max_long_term_frame_idx_plus1**). The value of **max_long_term_frame_idx_plus1** shall be in the range of 0 to **max_num_ref_frames**, inclusive.

## -remarks

The variable *MaxLongTermFrameIdx* is derived as follows:

* If **max_long_term_frame_idx_plus1** is equal to 0, *MaxLongTermFrameIdx* is set equal to "no long-term frame indices".
* If **max_long_term_frame_idx_plus1** is greater than 0, *MaxLongTermFrameIdx* is set equal to **max_long_term_frame_idx_plus1** − 1.

The operation of marking the current frame as a short-term reference is given by a flag present in the [**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_picture_control_codec_data_h264_flags_0080.md) structure with its corresponding **PictureOrderCountNumber** and **FrameDecodingOrderNumber** values indicated in the [associated picture control structure](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_codec_data_h264_0082_0.md).

The variable **max_num_ref_frames** is indicated by the maximum decoded picture buffer (DPB) capacity reported.

Note that for marking an instantaneous decoder refresh (IDR) frame as long-term reference, the proposed explicit mechanism is to mark it as short term reference first, by setting [**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_FLAG_0080_USED_AS_REFERENCE_PICTURE**](ne-d3d12umddi-d3d12ddi_video_encoder_picture_control_flags_0080.md) when calling [**EncodeFrame**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) for the IDR frame, and later promoting it to be a long-term reference frame using memory management operation '3' to mark a short-term reference picture as "used for long-term reference" and assign a long-term frame index to it.

Alternatively, if encoding an IDR frame and setting [**adaptive_ref_pic_marking_mode_flag**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_codec_data_h264_0082_0.md) = 1, the driver assumes that the client is attempting to set the H264 slice header **long_term_reference_flag** and will do so in the output bitstream for the [**EncodeFrame**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) call.

For more details about the picture marking process, see the H.264 specification, section 8.2.5.4 "Adaptive memory control decoded reference picture marking process".

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for more information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_codec_data_h264_0082_0.md)

[**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md)
