---
UID: NS:d3d12umddi.D3D12DDICAPS_VIDEO_ENCODER_INPUT_FORMAT_DATA_0080_2
tech.root: display
title: D3D12DDICAPS_VIDEO_ENCODER_INPUT_FORMAT_DATA_0080_2
ms.date: 02/16/2022
targetos: Windows
description: Learn more about the D3D12DDICAPS_VIDEO_ENCODER_INPUT_FORMAT_DATA_0080_2 structure.
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
req.typenames: D3D12DDICAPS_VIDEO_ENCODER_INPUT_FORMAT_DATA_0080_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDICAPS_VIDEO_ENCODER_INPUT_FORMAT_DATA_0080_2
f1_keywords:
 - D3D12DDICAPS_VIDEO_ENCODER_INPUT_FORMAT_DATA_0080_2
 - d3d12umddi/D3D12DDICAPS_VIDEO_ENCODER_INPUT_FORMAT_DATA_0080_2
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDICAPS_VIDEO_ENCODER_INPUT_FORMAT_DATA_0080_2
---

## -description

The **D3D12DDICAPS_VIDEO_ENCODER_INPUT_FORMAT_DATA_0080_2** structure is used to query whether a specified video encoding input format is supported.

## -struct-fields

### -field NodeIndex

[in] In a multi-adapter operation, **NodeIndex** indicates which physical adapter of the device that the operation applies to.

### -field Codec

[in] A [**D3D12DDI_VIDEO_ENCODER_CODEC_0080**](ne-d3d12umddi-d3d12ddi_video_encoder_codec_0080.md) value that specifies the codec to check support for.

### -field Profile

[in] A [**D3D12DDI_VIDEO_ENCODER_PROFILE_DESC_0080_2**](ns-d3d12umddi-d3d12ddi_video_encoder_profile_desc_0080_2.md) structure that specifies the profile to check support for.

### -field Format

[in] A [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) value that specifies the format setting to check support for.

> [!NOTE]
>
> This format definition includes the subsampling and bit-depth modes for the video encoding session. The driver is not responsible for handling the input subsampling/color conversion stages of video encoding; this is the responsibility of the host.

### -field IsSupported

[out] Indicates whether the given feature values are supported.

## -remarks

Format support for 4:2:0 with 8- and 10-bitdepth samples should be encoded using the following formats:

* DXGI_FORMAT_P010
* DXGI_FORMAT_NV12

The D3D runtime calls [**PFND3D12DDI_VIDEO_GETCAPS**](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md) with [**D3D12DDICAPS_TYPE_VIDEO_0080_ENCODER_INPUT_FORMAT**](ne-d3d12umddi-d3d12ddicaps_type_video_0020.md) specified as the capability type.

See [D3D12 video encoding](/windows-hardware/drivers/display/video-encoding-d3d12.md) for general information.

## -see-also

[**D3D12DDIARG_VIDEO_GETCAPS_0020**](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md)
