---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW
title: D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW
author: windows-driver-content
description: Arguments used to create a depth stencil view.
ms.assetid: 4ea81c63-03b8-4966-9dbf-8eee2af122d2
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW, D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW, 
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
req.typenames: D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW
product:
-	Windows
targetos: Windows
ms.custom: RS5
---

# D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW structure

## -description

Arguments used to create a depth stencil view.

## -struct-fields

### -field hDrvResource

A handle to the display driver resource.

### -field Format

A DXGI_FORMAT-typed value that indicates the pixel format of the depth stencil view.

### -field ResourceDimension

A [D3D12DDI_RESOURCE_DIMENSION](ne-d3d12umddi-d3d12ddi_resource_dimension.md) value that indicates the resource type and dimensionality of the base resource

### -field Flags

A [D3D12DDI_CREATE_DEPTH_STENCIL_VIEW_FLAGS](ne-d3d12umddi-d3d12ddi_create_depth_stencil_view_flags.md) flag.

### -field Tex1D

If the value in the *ResourceDimension* member is set to D3D12DDI_RD_TEXTURE1D, a member in the union that is contained in D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW that can hold a [D3D12DDIARG_TEX1D_DEPTH_STENCIL_VIEW](ns-d3d12umddi-d3d12ddiarg_tex1d_depth_stencil_view.md) structure for a one-dimensional texture

### -field Tex2D

If the value in the *ResourceDimension* member is set to D3D12DDI_RD_TEXTURE2D, a member in the union that is contained in D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW that can hold a [D3D12DDIARG_TEX2D_DEPTH_STENCIL_VIEW](ns-d3d12umddi-d3d12ddiarg_tex2d_depth_stencil_view.md) structure for a two-dimensional texture

### -field TexCube
 
If the value in the *ResourceDimension* member is set to D3D12DDI_RD_TEXTURECUBE, a member in the union that is contained in D3D12DDIARG_CREATE_DEPTH_STENCIL_VIEW that can hold a [D3D12DDIARG_TEXCUBE_DEPTH_STENCIL_VIEW](ns-d3d12umddi-d3d12ddiarg_texcube_depth_stencil_view.md) structure for a cube texture

## -remarks

## -see-also
