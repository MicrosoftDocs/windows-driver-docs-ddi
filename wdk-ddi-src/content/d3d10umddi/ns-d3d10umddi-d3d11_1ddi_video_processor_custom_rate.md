---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE
title: D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE (d3d10umddi.h)
description: Specifies a custom rate for frame-rate conversion or inverse telecine (IVTC).
old-location: display\d3d11_1ddi_video_processor_custom_rate.htm
ms.date: 12/09/2021
keywords: ["D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE structure"]
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE, D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE, display.d3d11_1ddi_video_processor_custom_rate
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
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE
f1_keywords:
 - D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE
 - d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE
---

# D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE structure

## -description

Specifies a custom rate for frame-rate conversion or inverse telecine (IVTC).

## -struct-fields

### -field CustomRate

The ratio of the output frame rate to the input frame rate, expressed as a [**DXGI_RATIONAL**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_rational) structure that holds a rational number.

### -field OutputFrames

The number of output frames that will be generated for every *N* input samples, where *N* = **InputFramesOrFields**.

### -field InputInterlaced

If **TRUE**, the input stream must be interlaced. Otherwise, the input stream must be progressive.

### -field InputFramesOrFields

The number of input fields or frames for every *N* output frames that will be generated, where *N* = **OutputFrames**.

## -remarks

The **CustomRate** member gives the rate conversion factor, while the remaining members define the pattern of input and output samples.

## -see-also

[**DXGI_RATIONAL**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_rational)
