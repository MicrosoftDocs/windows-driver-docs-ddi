---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_SCALE_SUPPORT_0032
title: D3D12DDI_VIDEO_SCALE_SUPPORT_0032
author: windows-driver-content
description: Video scale support.
old-location: display\d3d12ddi-video-scale-support-0032.htm
old-project: display
ms.assetid: 630ee3fe-f97a-4e82-83d7-4efd05bc5d6e
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 1, 2, 3, A, C, D, D3D12DDI_VIDEO_SCALE_SUPPORT_0032, D3D12DDI_VIDEO_SCALE_SUPPORT_0032 structure [Display Devices], E, I, L, O, P, R, S, T, U, V, _, d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_0032, display.d3d12ddi-video-scale-support-0032"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
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
-	d3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_SCALE_SUPPORT_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_SCALE_SUPPORT_0032
---

# D3D12DDI_VIDEO_SCALE_SUPPORT_0032 structure


## -description


Video scale support.


## -syntax


````
typedef struct _D3D12DDI_VIDEO_SCALE_SUPPORT_0032 {
  D3D12DDI_VIDEO_SIZE_RANGE_0032           OutputSizeRange;
  D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022  Flags;
} D3D12DDI_VIDEO_SCALE_SUPPORT_0032, D3D12DDI_VIDEO_SCALE_SUPPORT_0032;
````


## -struct-fields




### -field OutputSizeRange

Output size range.


### -field Flags

Flags.

