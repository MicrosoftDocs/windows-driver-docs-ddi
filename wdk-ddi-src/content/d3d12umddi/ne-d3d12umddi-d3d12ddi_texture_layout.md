---
UID: NE:d3d12umddi.D3D12DDI_TEXTURE_LAYOUT
title: D3D12DDI_TEXTURE_LAYOUT (d3d12umddi.h)
description: Specifies a texture layout.
old-location: display\d3d12ddi_texture_layout.htm
ms.date: 09/22/2022
keywords: ["D3D12DDI_TEXTURE_LAYOUT enumeration"]
ms.keywords: D3D12DDI_TEXTURE_LAYOUT, D3D12DDI_TEXTURE_LAYOUT enumeration [Display Devices], D3D12DDI_TL_64KB_TILE_STANDARD_SWIZZLE, D3D12DDI_TL_64KB_TILE_UNDEFINED_SWIZZLE, D3D12DDI_TL_DEVICE_DEPENDENT_SWIZZLE_0, D3D12DDI_TL_ROW_MAJOR, D3D12DDI_TL_UNDEFINED, d3d12umddi/D3D12DDI_TEXTURE_LAYOUT, d3d12umddi/D3D12DDI_TL_64KB_TILE_STANDARD_SWIZZLE, d3d12umddi/D3D12DDI_TL_64KB_TILE_UNDEFINED_SWIZZLE, d3d12umddi/D3D12DDI_TL_DEVICE_DEPENDENT_SWIZZLE_0, d3d12umddi/D3D12DDI_TL_ROW_MAJOR, d3d12umddi/D3D12DDI_TL_UNDEFINED, display.d3d12ddi_texture_layout
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
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_TEXTURE_LAYOUT
f1_keywords:
 - D3D12DDI_TEXTURE_LAYOUT
 - d3d12umddi/D3D12DDI_TEXTURE_LAYOUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_TEXTURE_LAYOUT
---

# D3D12DDI_TEXTURE_LAYOUT enumeration

## -description

A **D3D12DDI_TEXTURE_LAYOUT** value specifies a texture layout.

## -enum-fields

### -field D3D12DDI_TL_UNDEFINED

The texture layout is undefined, and is likely adapter-dependent.

### -field D3D12DDI_TL_ROW_MAJOR

The texture layout is row major.

### -field D3D12DDI_TL_64KB_TILE_UNDEFINED_SWIZZLE

The texture layout is a 64 KB tile with undefined swizzle.

### -field D3D12DDI_TL_64KB_TILE_STANDARD_SWIZZLE

The texture layout is a 64 KB tile with standard swizzle.

### -field D3D12DDI_TL_DEVICE_DEPENDENT_SWIZZLE_0

The texture layout is a device-dependent swizzle.


## -remarks

See [**D3D12_TEXTURE_LAYOUT**](/windows/win32/api/d3d12/ne-d3d12-d3d12_texture_layout) for more details about each layout.

## -see-also

[**D3D12_TEXTURE_LAYOUT**](/windows/win32/api/d3d12/ne-d3d12-d3d12_texture_layout)

[**D3D12DDIARG_CREATERESOURCE_0088**](ns-d3d12umddi-d3d12ddiarg_createresource_0088.md)
