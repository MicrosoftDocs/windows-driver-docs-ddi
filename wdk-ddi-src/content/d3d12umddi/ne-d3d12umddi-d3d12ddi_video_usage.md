---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_USAGE
title: D3D12DDI_VIDEO_USAGE (d3d12umddi.h)
description: A hint for the graphics driver to optimize for different scenarios.
old-location: display\d3d12ddi_video_usage.htm
ms.assetid: 663790EE-A9E3-4EBC-93C7-20DE0D759A26
ms.date: 05/10/2018
keywords: ["D3D12DDI_VIDEO_USAGE enumeration"]
ms.keywords: D3D12DDI_VIDEO_USAGE, D3D12DDI_VIDEO_USAGE enumeration [Display Devices], D3D12DDI_VIDEO_USAGE_NORMAL, D3D12DDI_VIDEO_USAGE_POWER, D3D12_VIDEO_USAGE_QUALITY, d3d12umddi/D3D12DDI_VIDEO_USAGE, d3d12umddi/D3D12DDI_VIDEO_USAGE_NORMAL, d3d12umddi/D3D12DDI_VIDEO_USAGE_POWER, d3d12umddi/D3D12_VIDEO_USAGE_QUALITY, display.d3d12ddi_video_usage
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_USAGE"
 - "D3D12DDI_VIDEO_USAGE"
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Windows 10, version 1709
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_VIDEO_USAGE
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_USAGE
---

# D3D12DDI_VIDEO_USAGE enumeration


## -description


A hint for the graphics driver to optimize for different scenarios.


## -enum-fields




### -field D3D12DDI_VIDEO_USAGE_NORMAL

Normal video playback.


### -field D3D12DDI_VIDEO_USAGE_POWER

Lower the power usage. This setting can lead to some reduction in video quality.


### -field D3D12DDI_VIDEO_USAGE_QUALITY

*D3D12_VIDEO_USAGE_QUALITY*

The best video quality possible. This setting is appropriate for tasks such as video editing, where quality is more important than speed. It is not appropriate for real-time playback.

