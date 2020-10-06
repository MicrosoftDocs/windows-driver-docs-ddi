---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_HISTOGRAM_DATA_0041
title: D3D12DDI_VIDEO_DECODE_HISTOGRAM_DATA_0041 (d3d12umddi.h)
description: Describes data for the video decode histogram.
ms.assetid: e2bd39ad-34d6-4e04-9e5c-754d5c3968b5
ms.date: 10/19/2018
keywords: ["D3D12DDI_VIDEO_DECODE_HISTOGRAM_DATA_0041 structure"]
ms.keywords: D3D12DDI_VIDEO_DECODE_HISTOGRAM_DATA_0041, D3D12DDI_VIDEO_DECODE_HISTOGRAM_DATA_0041,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3D12DDI_VIDEO_DECODE_HISTOGRAM_DATA_0041
targetos: Windows
tech.root: display
f1_keywords:
 - D3D12DDI_VIDEO_DECODE_HISTOGRAM_DATA_0041
 - d3d12umddi/D3D12DDI_VIDEO_DECODE_HISTOGRAM_DATA_0041
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_DECODE_HISTOGRAM_DATA_0041
product:
 - Windows
---

# D3D12DDI_VIDEO_DECODE_HISTOGRAM_DATA_0041 structure


## -description

Describes data for the video decode histogram.

## -struct-fields

### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.

### -field DecodeProfile

The decode profile GUID to retrieve the count of supported encryption GUIDs.

### -field Width

The width of the decoded frame.

### -field Height

The height of the decoded frame.

### -field DecodeFormat

The format of the decoded frame.

### -field Components

The components that the hardware supports.

### -field BinCount

The number of per component bins that are supported. BinCount must be >= 64, and must be a power of 2 (64, 128, 256, 512, etc.).

### -field CounterBitDepth

The bit depth of the bin counter. The counter is always stored in a 32 bit value and is therefore 32 bits or less. The counter is stored in the lower bits of the 32 bit storage. The upper bits are set to zero. If the in count exceeds this bit depth, the value is set to the maximum counter value. Valid values for CounterBitDepth are 16, 24, and 32.

