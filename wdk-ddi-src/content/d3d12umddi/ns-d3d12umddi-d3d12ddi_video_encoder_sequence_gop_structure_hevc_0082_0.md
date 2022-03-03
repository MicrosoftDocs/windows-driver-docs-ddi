---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_HEVC_0082_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_HEVC_0082_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_HEVC_0082_0 structure.
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
req.typenames: D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_HEVC_0082_0
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_HEVC_0082_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_HEVC_0082_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_HEVC_0082_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_HEVC_0082_0** structure represents the group of pictures (GOP) structure for HEVC video encoding.

## -struct-fields

### -field GOPLength

The distance between I-frames in the sequence, or the number of pictures in a GOP. If set to 0, only the first frame will be an I frame (infinite GOP).

### -field PPicturePeriod

The period for P-frames to be inserted within the GOP. If **GOPLength** is set to 0 for infinite GOP, **PPicturePeriod** must be greater than zero. An example usage follows:

Let *A* = **GOPLength** and *B* = **PPictureInterval**:

A=0; B=1 => IPPPPPPPP...
A=0; B=2 => IBPBPBPBP...
A=0; B=3 => IBBPBBPBB...
A=1; B=0 => IIIIIIIII...
A=2; B=1 => IPIPIPIPI...
A=3; B=1 => IPPIPPIPP...
A=3; B=2 => IBPIBPIBP...
A=4; B=3 => IBBPIBBPIBBP...

### -field log2_max_pic_order_cnt_lsb_minus4

Specifies the value of a variable *MaxPicOrderCntLsb* that is used in the decoding process for picture order count as specified in clause 8.2.1 of the specification as follows: `MaxPicOrderCntLsb = 2^(log2_max_pic_order_cnt_lsb_minus4 + 4)`. The value of **log2_max_pic_order_cnt_lsb_minus4** must be in the range of 0 to 12, inclusive.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE_0082_0**](ns-d3d12umddi-d3d12ddi_video_encoder_sequence_gop_structure_0082_0.md)
