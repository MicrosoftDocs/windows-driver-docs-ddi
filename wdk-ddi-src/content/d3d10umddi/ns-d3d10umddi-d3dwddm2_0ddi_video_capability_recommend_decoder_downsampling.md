---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
title: D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING (d3d10umddi.h)
description: D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING is used by the user-mode driver to recommend downsampling parameters that can be used to decode the stream in real-time.
old-location: display\d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling.htm
ms.date: 01/06/2023
keywords: ["D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING structure"]
ms.keywords: D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING, D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING, display.d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
f1_keywords:
 - D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
 - d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING
---

# D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING structure

## -description

**D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING** is used by the user-mode driver to recommend downsampling parameters that can be used to decode the stream in real-time. The driver provides these capabilities when its [**PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES**](nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md) function is called.

## -struct-fields

### -field pInputDesc

[in] Pointer to a [**D3D11_1DDI_VIDEO_DECODER_DESC**](ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md) structure containing the decode profile used and the resolution and format of the reference frames. This is the resolution/format to be downsampled (e.g. 4K, DXGI_FORMAT_P010).

### -field InputColorSpace

[in] A [**D3DDDI_COLOR_SPACE_TYPE**](ne-d3d10umddi-d3dddi_color_space_type.md) value that specifies the color space information of the reference frame data.

### -field pInputConfig

[in] Pointer to a [**D3D11_1DDI_VIDEO_DECODER_CONFIG**](ns-d3d10umddi-d3d11_1ddi_video_decoder_config.md) structure containing the configuration data associated with the decode profile.

### -field pFrameRate

[in] Pointer to a [**DXGI_RATIONAL**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_rational) structure containing the frame rate of the video content.

### -field pOutputDesc

[out] Pointer to a [**D3D11_1DDI_VIDEO_DECODER_DESC**](ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md) structure in which the driver returns the recommended resolution and the format of the output/display frames.  

The decode profile (**Guid**) member of **pOutputDesc** can be ignored.

### -field OutputColorSpace

[out] Location in which the driver returns the recommended [**D3DDDI_COLOR_SPACE_TYPE**](ne-d3d10umddi-d3dddi_color_space_type.md) color space information of the display frame data.

## -remarks

The driver recommends the down sample parameters such that the video stream can be decoded in real-time. If no down sample solution exists that can result in real-time decode, the driver should recommend the configuration that is closest to the real-time solution.

## -see-also

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY**](ne-d3d10umddi-d3dwddm2_0ddi_video_capability_query.md)

[**PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES**](nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md)
