---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_USAGE
title: D3D11_1DDI_VIDEO_USAGE (d3d10umddi.h)
description: Identifies how the decode device plays video.
old-location: display\d3d11_1ddi_video_usage.htm
ms.assetid: f107b9a8-d124-4fc3-80b3-dd20a87f9a86
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_USAGE enumeration"]
ms.keywords: D3D11_1DDI_VIDEO_USAGE, D3D11_1DDI_VIDEO_USAGE enumeration [Display Devices], D3D11_1DDI_VIDEO_USAGE_OPTIMAL_QUALITY, D3D11_1DDI_VIDEO_USAGE_OPTIMAL_SPEED, D3D11_1DDI_VIDEO_USAGE_PLAYBACK_NORMAL, d3d10umddi/D3D11_1DDI_VIDEO_USAGE, d3d10umddi/D3D11_1DDI_VIDEO_USAGE_OPTIMAL_QUALITY, d3d10umddi/D3D11_1DDI_VIDEO_USAGE_OPTIMAL_SPEED, d3d10umddi/D3D11_1DDI_VIDEO_USAGE_PLAYBACK_NORMAL, display.d3d11_1ddi_video_usage
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
req.typenames: D3D11_1DDI_VIDEO_USAGE
f1_keywords:
 - D3D11_1DDI_VIDEO_USAGE
 - d3d10umddi/D3D11_1DDI_VIDEO_USAGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_VIDEO_USAGE
---

# D3D11_1DDI_VIDEO_USAGE enumeration


## -description

Identifies how the decode device plays video.

## -enum-fields

### -field D3D11_1DDI_VIDEO_USAGE_PLAYBACK_NORMAL

Specifies that the device plays video at normal speed.

### -field D3D11_1DDI_VIDEO_USAGE_OPTIMAL_SPEED

Specifies that the device plays video at optimal speed.

### -field D3D11_1DDI_VIDEO_USAGE_OPTIMAL_QUALITY

Specifies that the device plays video at optimal quality.

## -remarks

A value of type <b>D3D11_1DDI_VIDEO_USAGE</b> is specified in the <b>Usage</b> member of a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_buffer_info">D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO</a> structure to help describe a decode device.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_buffer_info">D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO</a>