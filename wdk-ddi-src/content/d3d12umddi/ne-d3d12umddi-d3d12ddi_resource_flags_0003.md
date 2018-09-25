---
UID: NE:d3d12umddi.D3D12DDI_RESOURCE_FLAGS_0003
title: D3D12DDI_RESOURCE_FLAGS_0003
author: windows-driver-content
description: Specifies resource flag values.
old-location: display\d3d12ddi_resource_flags_0003.htm
ms.assetid: 595A4177-4A18-48D6-8B5C-D7D2FBD9FE9B
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D12DDI_RESOURCE_FLAGS_0003, D3D12DDI_RESOURCE_FLAGS_0003 enumeration [Display Devices], D3D12DDI_RESOURCE_FLAG_0003_CROSS_ADAPTER, D3D12DDI_RESOURCE_FLAG_0003_DEPTH_STENCIL, D3D12DDI_RESOURCE_FLAG_0003_NONE, D3D12DDI_RESOURCE_FLAG_0003_RENDER_TARGET, D3D12DDI_RESOURCE_FLAG_0003_SHADER_RESOURCE, D3D12DDI_RESOURCE_FLAG_0003_SIMULTANEOUS_ACCESS, D3D12DDI_RESOURCE_FLAG_0020_CONTENT_PROTECTION, D3D12DDI_RESOURCE_FLAG_0020_VIDEO_DECODE_REFERENCE_ONLY, D3D12DDI_RESOURCE_FLAG_0022_UNORDERED_ACCESS, d3d12umddi/D3D12DDI_RESOURCE_FLAGS_0003, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_CROSS_ADAPTER, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_DEPTH_STENCIL, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_NONE, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_RENDER_TARGET, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_SHADER_RESOURCE, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0003_SIMULTANEOUS_ACCESS, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0020_CONTENT_PROTECTION, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0020_VIDEO_DECODE_REFERENCE_ONLY, d3d12umddi/D3D12DDI_RESOURCE_FLAG_0022_UNORDERED_ACCESS, display.d3d12ddi_resource_flags_0003
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3D12DDI_RESOURCE_FLAGS_0003
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_RESOURCE_FLAGS_0003
---

# D3D12DDI_RESOURCE_FLAGS_0003 enumeration


## -description


Specifies resource flag values.


## -enum-fields




### -field D3D12DDI_RESOURCE_FLAG_0003_NONE

Constant for no flags.


### -field D3D12DDI_RESOURCE_FLAG_0003_RENDER_TARGET

Render target.


### -field D3D12DDI_RESOURCE_FLAG_0003_DEPTH_STENCIL

Depth stencil.


### -field D3D12DDI_RESOURCE_FLAG_0003_CROSS_ADAPTER

Cross adapter.


### -field D3D12DDI_RESOURCE_FLAG_0003_SIMULTANEOUS_ACCESS

Simultaneous access.


### -field D3D12DDI_RESOURCE_FLAG_0003_SHADER_RESOURCE

Shader resource.


### -field D3D12DDI_RESOURCE_FLAG_0020_VIDEO_DECODE_REFERENCE_ONLY

This resource may only be used as a decode reference frame. It may only be written to or read by the video decode operation.


### -field D3D12DDI_RESOURCE_FLAG_0020_CONTENT_PROTECTION

The resource supports content protection.


### -field D3D12DDI_RESOURCE_FLAG_0022_UNORDERED_ACCESS

Unordered access. This value is available as a resource flag for the fallback plans.

### -field D3D12DDI_RESOURCE_FLAG_0041_ONLY_NON_RT_DS_TEXTURE_PLACEMENT

Not currently used.

### -field D3D12DDI_RESOURCE_FLAG_0041_ONLY_RT_DS_TEXTURE_PLACEMENT

Not currently used.

### -field D3D12DDI_RESOURCE_FLAG_0041_4MB_ALIGNED

Not currently used.