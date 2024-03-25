---
UID: NE:d3d12umddi.D3D12DDI_RESOLVE_MODE
title: D3D12DDI_RESOLVE_MODE (d3d12umddi.h)
description: Specifies a Render Pass resolve operation in display driver development.
ms.date: 05/24/2022
keywords: ["D3D12DDI_RESOLVE_MODE enumeration"]
ms.keywords: D3D12DDI_RESOLVE_MODE, D3D12DDI_RESOLVE_MODE, Render Pass
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_RESOLVE_MODE
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_RESOLVE_MODE
 - d3d12umddi/D3D12DDI_RESOLVE_MODE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RESOLVE_MODE
dev_langs:
 - c++
---

# D3D12DDI_RESOLVE_MODE enumeration

## -description

Specifies a Render Pass resolve operation in display driver development.

## -enum-fields

### -field D3D12DDI_RESOLVE_MODE_DECOMPRESS:0

Resolves compressed source samples to their uncompressed values. When using this operation, the source and destination resources must have the same sample count, unlike the min, max, and average operations that require the destination to have a sample count of 1.

### -field D3D12DDI_RESOLVE_MODE_MIN:1

Resolves the source samples to their minimum value. It can be used with any render target or depth stencil format.

### -field D3D12DDI_RESOLVE_MODE_MAX:2

Resolves the source samples to their maximum value. It can be used with any render target or depth stencil format.

### -field D3D12DDI_RESOLVE_MODE_AVERAGE:3

Resolves the source samples to their average value. It can be used with any non-integer render target format, including the depth plane. It can't be used with integer render target formats, including the stencil plane.

### -field D3D12DDI_RESOLVE_MODE_ENCODE_SAMPLER_FEEDBACK_0073:4

Transcode sampler feedback maps to an application-usable format.

### -field D3D12DDI_RESOLVE_MODE_DECODE_SAMPLER_FEEDBACK_0073:5

Transcode sampler feedback maps from an application-usable format.
