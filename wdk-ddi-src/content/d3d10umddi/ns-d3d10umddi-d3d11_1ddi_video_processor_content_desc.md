---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC
title: D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC (d3d10umddi.h)
description: Describes a video stream for a video processor.
old-location: display\d3d11_1ddi_video_processor_content_desc.htm
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC structure"]
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC, D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC, display.d3d11_1ddi_video_processor_content_desc
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
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC
f1_keywords:
 - D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC
 - d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC
---

# D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC structure

## -description

Describes a video stream for a video processor.

## -struct-fields

### -field InputFrameFormat

A member of the [**D3D11_1DDI_VIDEO_FRAME_FORMAT**](ne-d3d10umddi-d3d11_1ddi_video_frame_format.md) enumeration that describes how the video stream is interlaced.

### -field InputFrameRate

The frame rate of the input video stream, specified as a [**DXGI_RATIONAL**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_rational) structure.

### -field InputWidth

The width of the input frames, in pixels.

### -field InputHeight

The height of the input frames, in pixels.

### -field OutputFrameRate

The frame rate of the output video stream, specified as a [**DXGI_RATIONAL**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_rational) structure.

### -field OutputWidth

The width of the output frames, in pixels.

### -field OutputHeight

The height of the output frames, in pixels.

### -field Usage

A member of the [**D3D11_1DDI_VIDEO_USAGE**](ne-d3d10umddi-d3d11_1ddi_video_usage.md) enumeration that describes how the video processor will be used. The value indicates the desired trade-off between speed and video quality. The driver uses this flag as a hint when it creates the video processor.

## -see-also

[**D3D11_1DDI_VIDEO_FRAME_FORMAT**](ne-d3d10umddi-d3d11_1ddi_video_frame_format.md)

[**D3D11_1DDI_VIDEO_USAGE**](ne-d3d10umddi-d3d11_1ddi_video_usage.md)

[**DXGI_RATIONAL**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_rational)
