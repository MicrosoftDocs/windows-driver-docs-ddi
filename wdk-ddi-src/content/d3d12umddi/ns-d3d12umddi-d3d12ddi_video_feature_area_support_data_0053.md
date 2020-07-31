---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_FEATURE_AREA_SUPPORT_DATA_0053
title: D3D12DDI_VIDEO_FEATURE_AREA_SUPPORT_DATA_0053 (d3d12umddi.h)
description: The data used in the video capability check for feature area support.
ms.assetid: 5c1ad079-62fd-41cd-95d5-58b22985a808
ms.date: 10/19/2018
keywords: ["D3D12DDI_VIDEO_FEATURE_AREA_SUPPORT_DATA_0053 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_FEATURE_AREA_SUPPORT_DATA_0053"
 - "D3D12DDI_VIDEO_FEATURE_AREA_SUPPORT_DATA_0053"
ms.keywords: D3D12DDI_VIDEO_FEATURE_AREA_SUPPORT_DATA_0053, D3D12DDI_VIDEO_FEATURE_AREA_SUPPORT_DATA_0053, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_VIDEO_FEATURE_AREA_SUPPORT_DATA_0053
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_VIDEO_FEATURE_AREA_SUPPORT_DATA_0053
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_VIDEO_FEATURE_AREA_SUPPORT_DATA_0053 structure

## -description

The data used in the video capability check for feature area support.

## -struct-fields

### -field NodeIndex

In multi-adapter operation, this value indicates which physical adapter of the device this operation applies to.

### -field VideoDecodeSupport

Indicates whether video decode is supported.

### -field VideoProcessSupport

Indicates whether video process is supported.

### -field VideoEncodeSupport
 
Indicates whether video encode is supported.

## -remarks

## -see-also
