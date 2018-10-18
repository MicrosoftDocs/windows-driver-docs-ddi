---
UID: NS:d3d12umddi.D3D12DDIARG_TEX2D_SHADER_RESOURCE_VIEW_0002
title: D3D12DDIARG_TEX2D_SHADER_RESOURCE_VIEW_0002
author: windows-driver-content
description: Describes a two-dimensional (2-D) texture that is used to create a shader resource view.
ms.assetid: bc3135d7-ca2c-4f3d-aafd-87247af0d440
ms.date: 
ms.topic: struct
ms.keywords: D3D12DDIARG_TEX2D_SHADER_RESOURCE_VIEW_0002, D3D12DDIARG_TEX2D_SHADER_RESOURCE_VIEW_0002, 
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
req.typenames: D3D12DDIARG_TEX2D_SHADER_RESOURCE_VIEW_0002
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDIARG_TEX2D_SHADER_RESOURCE_VIEW_0002
product:
-	Windows
targetos: Windows
---

# D3D12DDIARG_TEX2D_SHADER_RESOURCE_VIEW_0002 structure

## -description

Describes a two-dimensional (2-D) texture that is used to create a shader resource view.

## -struct-fields

### -field MostDetailedMip

The identifier of the most detailed MIP-map.

### -field FirstArraySlice

The identifier of the first array slice.

### -field MipLevels

The number of MIP-map levels for the texture.

### -field ArraySize

The number of array slices for the texture.

### -field PlaneSlice

The index (plane slice number) of the plane to use in the texture.

### -field ResourceMinLODClamp
 
A value to clamp sample LOD values to. For example, if you specify 2.0f for the clamp value, you ensure that no individual sample accesses a mip level less than 2.0f.

## -remarks

## -see-also
