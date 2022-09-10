---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS (d3d10umddi.h)
description: Defines features that a Microsoft Direct3D 11 video processor can support.
old-location: display\d3d11_1ddi_video_processor_feature_caps.htm
ms.date: 08/22/2022
keywords: ["D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS enumeration"]
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS enumeration [Display Devices], D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_FILL, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_STREAM, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_CONSTRICTION, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LEGACY, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LUMA_KEY, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_MIRROR, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_ASPECT_RATIO, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_SHADER_USAGE, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ROTATION, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO, d3d10umddi/, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_FILL, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_STREAM, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_CONSTRICTION, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LEGACY, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LUMA_KEY, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_MIRROR, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_ASPECT_RATIO, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_SHADER_USAGE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ROTATION, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO, display.d3d11_1ddi_video_processor_feature_caps
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS
f1_keywords:
 - D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS
 - d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS enumeration

## -description

Defines features that a Microsoft Direct3D 11 video processor can support.

## -enum-fields

### -field D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_FILL:0x1

The video processor can set alpha values on the output pixels. For more information, see [**VideoProcessorSetOutputAlphaFillMode**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md).

### -field D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_CONSTRICTION:0x2

The video processor can downsample the video output. For more information, see [**VideoProcessorSetOutputConstriction**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputconstriction.md).

### -field D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LUMA_KEY:0x4

The video processor can perform luma keying. For more information, see [**VideoProcessorSetStreamLumaKey**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamlumakey.md).

### -field D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE:0x8

The video processor can apply alpha values from color palette entries.

### -field D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LEGACY:0x10

The driver does not support the DXVA-HDDDI. If this capability flag is set, the video processor has the following limitations:

* A maximum of two streams are supported:
  * The first stream must be either NV12 or YUY2.
  * The second stream must be AYUV, AI44, or IA44.
* Image adjustment (proc amp) controls are applied to the entire video processing blit, rather than per stream.
* Support for per-stream planar alpha is not reliable. (Per-pixel alpha is supported, however.)

### -field D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO:0x20

The video processor can support 3-D stereo video. For more information, see [**VideoProcessorSetStreamStereoFormat**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md).

### -field D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ROTATION:0x40

The video processor is capable of rotating the input stream by 90, 180, or 270 degrees (clockwise).

### -field D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_STREAM:0x80

The video processor supports blending input streams using a per-stream alpha value.

### -field D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_ASPECT_RATIO:0x100

The video processor supports explicit aspect ratios for the source and destination.

### -field D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_MIRROR:0x200

Indicates that the driver supports [**VideoProcessorSetStreamMirror**](nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetstreammirror.md).

Supported starting with Windows 10.

### -field D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_SHADER_USAGE:0x400

Indicates that the hardware can benefit from a hint as to whether a shader might be used to read the output of [**VideoProcessorBlt**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md). This should only be set by hardware that support multi-plane overlays.

### -field D3DWDDM2_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_METADATA_HDR10:0x800

Indicates that the driver will properly convert the video data based on the specified HDR10 metadata. Supported starting in Windows 10.

## -see-also

[**VideoProcessorBlt**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md)

[**VideoProcessorSetOutputAlphaFillMode**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md)

[**VideoProcessorSetOutputConstriction**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputconstriction.md)

[**VideoProcessorSetStreamLumaKey**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamlumakey.md)

[**VideoProcessorSetStreamMirror**](nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetstreammirror.md)

[**VideoProcessorSetStreamStereoFormat**](nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md)
