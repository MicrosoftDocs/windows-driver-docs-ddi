---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_USAGE
title: D3D12DDI_VIDEO_USAGE
author: windows-driver-content
description: A hint for the graphics driver to optimize for different scenarios.
old-location: display\d3d12ddi_video_usage.htm
old-project: display
ms.assetid: 663790EE-A9E3-4EBC-93C7-20DE0D759A26
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 1, 2, 3, A, D, D3D12DDI_VIDEO_USAGE, D3D12DDI_VIDEO_USAGE enumeration [Display Devices], D3D12DDI_VIDEO_USAGE_NORMAL, D3D12DDI_VIDEO_USAGE_POWER, D3D12_VIDEO_USAGE_QUALITY, E, G, I, O, S, U, V, _, d3d12umddi/D3D12DDI_VIDEO_USAGE, d3d12umddi/D3D12DDI_VIDEO_USAGE_NORMAL, d3d12umddi/D3D12DDI_VIDEO_USAGE_POWER, d3d12umddi/D3D12_VIDEO_USAGE_QUALITY, display.d3d12ddi_video_usage"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_USAGE
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_USAGE
---

# D3D12DDI_VIDEO_USAGE enumeration


## -description


A hint for the graphics driver to optimize for different scenarios.


## -syntax


````
typedef enum D3D12DDI_VIDEO_USAGE { 
  D3D12DDI_VIDEO_USAGE_NORMAL  = 0,
  D3D12DDI_VIDEO_USAGE_POWER   = 1,
  D3D12_VIDEO_USAGE_QUALITY    = 2
} D3D12DDI_VIDEO_USAGE;
````


## -enum-fields




### -field D3D12DDI_VIDEO_USAGE_NORMAL

Normal video playback.


### -field D3D12DDI_VIDEO_USAGE_POWER

Lower the power usage. This setting can lead to some reduction in video quality.


### -field D3D12DDI_VIDEO_USAGE_QUALITY




#### - D3D12_VIDEO_USAGE_QUALITY

The best video quality possible. This setting is appropriate for tasks such as video editing, where quality is more important than speed. It is not appropriate for real-time playback.

