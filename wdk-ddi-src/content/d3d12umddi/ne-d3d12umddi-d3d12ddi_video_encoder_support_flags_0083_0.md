---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0083_0
tech.root: display
title: D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0083_0
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0083_0 enumeration.
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
 - D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0083_0
f1_keywords:
 - D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0083_0
 - d3d12umddi/D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0083_0
dev_langs:
 - c++
---

## -description

The **D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAGS_0083_0** enumeration reports the support for a given configuration.

## -enum-fields

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_NONE:0x00

No flags are set (indicates no support).

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_GENERAL_SUPPORT_OK:0x01

Indicates whether the given configuration is generally supported by the encoder, in combination with the remaining flags to convey certain limitations or no general support. The D3D12 Debug layer can provide further information.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_RATE_CONTROL_RECONFIGURATION_AVAILABLE:0x02

Indicates support for changing the rate control in the middle of the encoding session.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_RESOLUTION_RECONFIGURATION_AVAILABLE:0x04

Indicates support for changing the resolution in the middle of the encoding session.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_RATE_CONTROL_VBV_SIZE_CONFIG_AVAILABLE:0x08

When set, enables configuring the video buffering verifier (VBV) initial fullness and capacity for rate control algorithms.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_RATE_CONTROL_FRAME_ANALYSIS_AVAILABLE:0x10

Indicates support for rate control modes that involve frame analysis to optimize the bitrate usage at the cost of slower performance.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_RECONSTRUCTED_FRAMES_REQUIRE_TEXTURE_ARRAYS:0x20

When set, textures that refer reconstructed pictures can only be referenced as a texture array, as opposed to an array of separate texture 2D resources with each resource having array size of 1. When this capability is not required, there is more flexibility for the host. This is important for scenarios where the resolution changes frequently and the decoded picture buffer (DPB) needs to be flushed for an instantaneous decoder refresh (IDR) frame, because a texture array can only be allocated and deallocated as an single unit, but separate texture 2D resources can be allocated and deallocated individually.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_RATE_CONTROL_DELTA_QP_AVAILABLE:0x40

Indicates support for delta quantization parameter (QP) usage in rate control.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_SUBREGION_LAYOUT_RECONFIGURATION_AVAILABLE:0x80

Indicates support for dynamic subregion layout changes during an encoding session.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_RATE_CONTROL_ADJUSTABLE_QP_RANGE_AVAILABLE:0x100

Indicates support for adjustable QP range in rate control.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_RATE_CONTROL_INITIAL_QP_AVAILABLE:0x200

Indicates support for adjustable initial QP in rate control.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_RATE_CONTROL_MAX_FRAME_SIZE_AVAILABLE:0x400

Indicates support for setting a maximum cap in the bitrate algorithm per each encoded frame.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_SEQUENCE_GOP_RECONFIGURATION_AVAILABLE:0x800

Indicates support for dynamic group of pictures (GOP) changes during an encoding session.

### -field D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_MOTION_ESTIMATION_PRECISION_MODE_LIMIT_AVAILABLE::0x1000

If the driver sets this bit, the user can limit the precision used for motion search on frame encode.

## -remarks

 When set, **D3D12DDI_VIDEO_ENCODER_SUPPORT_FLAG_0083_0_GENERAL_SUPPORT_OK** indicates general support, which is defined as follows:

* There is support to allocate all buffers with [**D3D12_MEMORY_POOL_L0**](/windows/win32/api/d3d12/ne-d3d12-d3d12_memory_pool). This is always system memory, but still a D3D12 buffer.

* There is support to allocate all buffers with [**D3D12_MEMORY_POOL_L1**](/windows/win32/api/d3d12/ne-d3d12-d3d12_memory_pool), the default pool, including those allocated with [**D3D12DDI_CPU_PAGE_PROPERTY_NOT_AVAILABLE**](/windows/win32/api/d3d12/ne-d3d12-d3d12_cpu_page_property).

The rest of the flags are combined to convey further information.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12) for general information.

## -see-also

[**D3D12DDIARG_VIDEO_GETCAPS_0020**](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md)

[**D3D12DDICAPS_VIDEO_ENCODER_SUPPORT_DATA_0083_0**](ns-d3d12umddi-d3d12ddicaps_video_encoder_support_data_0083_0.md)
