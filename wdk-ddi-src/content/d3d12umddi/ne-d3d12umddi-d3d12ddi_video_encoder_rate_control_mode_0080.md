---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080
---

## -description

The **D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080** enumeration lists the possible rate control modes.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080_ABSOLUTE_QP_MAP

Indicates no rate control budgeting. Each [**EncodeFrame**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md) call will interpret the quantization parameter (QP) values in **pRateControlQPMap** as a map of absolute values.

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080_CQP

Indicates constant quantization parameter (CQP) rate control mode.

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080_CBR

Indicates constant bit rate (CBR) rate control mode.

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080_VBR

Indicates variable bit rate (VBR) rate control mode.

### -field D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_MODE_0080_QVBR

Indicates constant quality target rate variable bit rate (QVBR) rate control mode.

## -remarks

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDI_VIDEO_ENCODER_RATE_CONTROL_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_rate_control_0080_2.md)

[**PFND3D12DDI_VIDEO_ENCODE_FRAME_0082_0**](nc-d3d12umddi-pfnd3d12ddi_video_encode_frame_0082_0.md)
