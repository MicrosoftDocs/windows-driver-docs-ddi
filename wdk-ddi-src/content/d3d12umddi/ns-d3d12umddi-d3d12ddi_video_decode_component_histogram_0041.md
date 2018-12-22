---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_COMPONENT_HISTOGRAM_0041
title: D3D12DDI_VIDEO_DECODE_COMPONENT_HISTOGRAM_0041
description:
ms.assetid: 790e3ae9-22da-4b5c-a9b0-e727689e9394
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDI_VIDEO_DECODE_COMPONENT_HISTOGRAM_0041, D3D12DDI_VIDEO_DECODE_COMPONENT_HISTOGRAM_0041,
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
req.typenames: D3D12DDI_VIDEO_DECODE_COMPONENT_HISTOGRAM_0041
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_COMPONENT_HISTOGRAM_0041
product: 
- Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_VIDEO_DECODE_COMPONENT_HISTOGRAM_0041 structure

## -description

Describes the histogram output buffer for a single component.

## -struct-fields

### -field Offset

The offset location in pBuffer to write the component histogram. Set to zero when this component is disabled.

> **Note** This value must be 256-byte aligned.

### -field hDrvBuffer

The target buffer for the hardware to write the components histogram. Set to a nullptr when the component histogram is disabled.

