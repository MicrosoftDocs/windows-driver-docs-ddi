---
UID: NS:d3d10umddi.D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM
title: D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM
author: windows-driver-content
description: Contains decode histogram output buffer information such as decode profile, resolution, and format.
ms.assetid: 29d827ff-d958-44dc-8206-cb5017115265
ms.date:
ms.topic: struct
ms.keywords: D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM, D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM,
req.header: d3d10umddi.h
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
req.typenames: D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM
product: 
- Windows
targetos: Windows
tech.root: display
---

# D3DWDDM2_4DDI_VIDEO_DECODER_HISTOGRAM structure

## -description

Contains decode histogram output buffer information such as decode profile, resolution, and format.

## -struct-fields

### -field Offset

The offset location in hBuffer to write the component histogram.

### -field hBuffer

The target buffer for hardware to write the components histogram. Set to a nullptr when the component histogram is disabled.

## -remarks

## -see-also
