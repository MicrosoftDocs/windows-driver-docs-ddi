---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_LIST_MODIFICATION_OPERATION_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_LIST_MODIFICATION_OPERATION_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_LIST_MODIFICATION_OPERATION_0082_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_LIST_MODIFICATION_OPERATION_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_LIST_MODIFICATION_OPERATION_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_LIST_MODIFICATION_OPERATION_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_LIST_MODIFICATION_OPERATION_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_REFERENCE_PICTURE_LIST_MODIFICATION_OPERATION_0082_0** structure represents a picture list modification operation for H.264 video encoding.

## -struct-fields

### -field modification_of_pic_nums_idc

Together with **abs_diff_pic_num_minus1** or **long_term_pic_num**, specifies which of the reference pictures are re-mapped. The values of **modification_of_pic_nums_idc** are specified in Table 7-7 of the H.264 specification. The first **modification_of_pic_nums_idc** that follows immediately after *ref_pic_list_modification_flag_l0* or *ref_pic_list_modification_flag_l1* shall not be equal to 3.

### -field abs_diff_pic_num_minus1

Plus 1 specifies the absolute difference between the picture number of the picture being moved to the current index in the list and the picture number prediction value. **abs_diff_pic_num_minus1** shall be in the range of 0 to *MaxPicNum* − 1. The allowed values of **abs_diff_pic_num_minus1** are further restricted as specified in clause 8.2.4.3.1 of the H.264 specification.

### -field long_term_pic_num

Specifies the long-term picture number of the picture being moved to the current index in the list. When decoding a coded frame, **long_term_pic_num** shall be equal to a *LongTermPicNum* assigned to one of the reference frames or complementary reference field pairs marked as "used for long-term reference". When decoding a coded field, **long_term_pic_num** shall be equal to a *LongTermPicNum* assigned to one of the reference fields marked as "used for long-term reference".

## -remarks

For modification details, refer to the H.264 specification, section 7.4.3.1 "Reference picture list modification semantics".

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_picture_control_codec_data_h264_0082_0.md)
