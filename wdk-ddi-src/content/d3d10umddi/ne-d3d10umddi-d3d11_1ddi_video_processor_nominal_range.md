---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE
title: D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE (d3d10umddi.h)
description: Indicates the luminance range of YUV data.
old-location: display\d3d11_1ddi_video_processor_nominal_range.htm
ms.assetid: E8D77D49-9E7C-45B3-850C-1E814B44464B
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE enumeration"]
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE, D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE enumeration [Display Devices], D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE_0_255, D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE_16_235, D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE_UNDEFINED, DXVAHDDDI_NOMINAL_RANGE, DXVAHDDDI_NOMINAL_RANGE enumeration [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE_0_255, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE_16_235, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE_UNDEFINED, display.d3d11_1ddi_video_processor_nominal_range
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE
f1_keywords:
 - D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE
 - d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - DXVAHDDDI_NOMINAL_RANGE
---

# D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE enumeration


## -description

Indicates the luminance range of YUV data.

## -enum-fields

### -field D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE_UNDEFINED

The driver default value, which is the <i>studio luminance range</i> of 16 to 235, inclusive [16, 235].

### -field D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE_16_235

The <i>studio luminance range</i> of 16 to 235, inclusive [16, 235].

### -field D3D11_1DDI_VIDEO_PROCESSOR_NOMINAL_RANGE_0_255

The <i>full luminance range</i>, or <i>extended range</i>, of 0 to 255, inclusive [0, 255].

## -remarks

For more information on luminance range, see <a href="/windows-hardware/drivers/display/yuv-format-ranges">YUV format ranges in Windows 8.1</a>.