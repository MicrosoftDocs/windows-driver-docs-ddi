---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
title: D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
author: windows-driver-content
description: Video decode format count data.
old-location: display\d3d12ddi-video-decode-format-count-data-0032.htm
old-project: display
ms.assetid: 3d28fe10-1dfc-4017-9ab0-d8b8e2d45448
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032, display.d3d12ddi-video-decode-format-count-data-0032, d3d12umddi/D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032, D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032 structure [Display Devices]
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
-	D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
---

# D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032 structure


## -description


Video decode format count data.


## -syntax


````
typedef struct _D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032 {
  UINT                                      NodeIndex;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020  Configuration;
  UINT                                      FormatCount;
} D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032, D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032;
````


## -struct-fields




### -field NodeIndex

Node index.


### -field Configuration

Configuration.


### -field FormatCount

Format count.

