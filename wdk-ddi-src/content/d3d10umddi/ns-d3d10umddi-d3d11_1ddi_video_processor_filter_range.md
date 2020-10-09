---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE
title: D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE (d3d10umddi.h)
description: Defines the range of supported values for an image filter.
old-location: display\d3d11_1ddi_video_processor_filter_range.htm
ms.assetid: 9dc93d92-ccdc-488b-a5dd-a2efe783cbb3
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE structure"]
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE, D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE, display.d3d11_1ddi_video_processor_filter_range
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
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE
f1_keywords:
 - D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE
 - d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE
---

# D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE structure


## -description

Defines the range of supported values for an image filter.

## -struct-fields

### -field Minimum

The minimum value of the filter.

### -field Maximum

The maximum value of the filter.

### -field Default

The default value of the filter.

### -field Multiplier

A multiplier. Use the following formula to translate the filter setting into the actual filter value: <i>Actual Value</i> = <i>Set Value</i> Ã— <i>Multiplier</i>.

## -remarks

The multiplier enables the filter range to have a fractional step value.

For example, a hue filter might have an actual range of [-180.0 … +180.0] with a step size of 0.25. The device would report the following range and multiplier:<ul>
<li>Minimum: -720</li>
<li>Maximum: +720</li>
<li>Multiplier: 0.25</li>
</ul>


In this case, a filter value of 2 would be interpreted by the device as 0.50 (or 2 Ã— 0.25).

The device should use a multiplier that can be represented exactly as a base-2 fraction.

