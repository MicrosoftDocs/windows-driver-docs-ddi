---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_COMPONENT_HISTOGRAM_0041
title: D3D12DDI_VIDEO_DECODE_COMPONENT_HISTOGRAM_0041
author: windows-driver-content
description:
ms.assetid: 790e3ae9-22da-4b5c-a9b0-e727689e9394
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_DECODE_COMPONENT_HISTOGRAM_0041
product: Windows
targetos: Windows
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

