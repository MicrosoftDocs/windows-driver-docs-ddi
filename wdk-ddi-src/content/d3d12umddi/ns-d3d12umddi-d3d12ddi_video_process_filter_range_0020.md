---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_FILTER_RANGE_0020
title: D3D12DDI_VIDEO_PROCESS_FILTER_RANGE_0020
description: Defines the range of supported values for an image filter.
old-location: display\d3d12ddi_video_process_filter_range.htm
ms.assetid: D77D1542-2730-456A-BC99-3507C4377C77
ms.date: 04/16/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_FILTER_RANGE_0020, D3D12DDI_VIDEO_PROCESS_FILTER_RANGE_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_FILTER_RANGE_0020, display.d3d12ddi_video_process_filter_range
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_PROCESS_FILTER_RANGE_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_FILTER_RANGE_0020
---

# D3D12DDI_VIDEO_PROCESS_FILTER_RANGE_0020 structure


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

A multiplier. Use this formula to translate the filter setting into the actual filter value: Actual Value = Set Value × Multiplier.


## -remarks



The multiplier enables the filter range to have a fractional step value.
For example, a hue filter might have an actual range of [–180.0 ... +180.0] with a step size of 0.25. The device would report the following range and multiplier:


* Minimum: –720
* Maximum: +720
* Multiplier: 0.25


In this case, a filter value of 2 would be interpreted by the device as 0.50, which is 2 × 0.25.

The device should use a multiplier that can be represented exactly as a base-2 fraction.



