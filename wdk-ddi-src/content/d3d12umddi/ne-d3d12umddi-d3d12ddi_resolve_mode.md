---
UID: NE:d3d12umddi.D3D12DDI_RESOLVE_MODE
title: D3D12DDI_RESOLVE_MODE
author: windows-driver-content
description: Specifies a Render Pass resolve operation in display driver development.
ms.assetid: 0af9440b-065d-4324-9888-f5d2119103d9
ms.date: 10/19/2018
ms.topic: enum
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
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_RESOLVE_MODE
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_RESOLVE_MODE enumeration

## -description

Specifies a Render Pass resolve operation in display driver development.

## -enum-fields

### -field D3D12DDI_RESOLVE_MODE_DECOMPRESS

Resolves compressed source samples to their uncompressed values. When using this operation, the source and destination resources must have the same sample count, unlike the min, max, and average operations that require the destination to have a sample count of 1.

### -field D3D12DDI_RESOLVE_MODE_MIN

Resolves the source samples to their minimum value. It can be used with any render target or depth stencil format.

### -field D3D12DDI_RESOLVE_MODE_MAX

Resolves the source samples to their maximum value. It can be used with any render target or depth stencil format.

### -field D3D12DDI_RESOLVE_MODE_AVERAGE 

Resolves the source samples to their average value. It can be used with any non-integer render target format, including the depth plane. It can't be used with integer render target formats, including the stencil plane.

## -remarks

## -see-also
