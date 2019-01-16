---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
title: D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
description: Video decode format count data.
old-location: display\d3d12ddi-video-decode-format-count-data-0032.htm
ms.assetid: 3d28fe10-1dfc-4017-9ab0-d8b8e2d45448
ms.date: 04/16/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032, D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032, display.d3d12ddi-video-decode-format-count-data-0032
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
---

# D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032 structure


## -description


Retrieves the number of formats supported for a given decode configuration.


## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field Configuration

Specifies the decode configuration for the list of formats. See [D3D12DDI_VIDEO_DECODE_CONFIGURATION](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md) for more information.


### -field FormatCount

The count of formats supported for the given node and configuration.

