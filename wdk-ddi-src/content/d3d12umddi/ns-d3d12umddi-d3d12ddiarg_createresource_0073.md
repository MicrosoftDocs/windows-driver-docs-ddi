---
UID: NS:d3d12umddi.D3D12DDIARG_CREATERESOURCE_0073
title: D3D12DDIARG_CREATERESOURCE_0073
ms.date: 03/24/2020
tech.root: display
targetos: Windows
description: The D3D12DDIARG_CREATERESOURCE_0073 structure contains information used to create or calculate the size of a resource.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDIARG_CREATERESOURCE_0073
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATERESOURCE_0073
f1_keywords:
 - D3D12DDIARG_CREATERESOURCE_0073
 - d3d12umddi/D3D12DDIARG_CREATERESOURCE_0073
dev_langs:
 - c++
---

## -description

The **D3D12DDIARG_CREATERESOURCE_0073** structure contains information needed to describe the creation or size calculation of a resource.

## -struct-fields

### -field ReuseBufferGPUVA

The GPU virtual address that this resource should have, if it does not need a new one assigned.

### -field ResourceType

A [**D3D12DDI_RESOURCE_TYPE**](ne-d3d12umddi-d3d12ddi_resource_type.md) that specifies the type of resource.

### -field Width

The width of the resource. This value is in texels if the resource is a texture, or in bytes if the resource is a buffer.

### -field Height

The height of the resource, in texels. This member applies to two-dimensional and three-dimensional textures only.

### -field DepthOrArraySize

The depth, or array size of the resource used when the resource is three-dimensional, or arrayed respectively.

### -field MipLevels

The number of mip levels the resource has.

### -field Format

Specifies how the resource's data is to be interpreted, using a [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) enumeration value.

### -field SampleDesc

A [**DXGI_SAMPLE_DESC**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_sample_desc) structure that specifies the sample count and quality level of this resource, as it relates to multisampling.

### -field Layout

A [**D3D12_TEXTURE_LAYOUT**](/windows/win32/api/d3d12/ne-d3d12-d3d12_texture_layout) that specifies details related to how the memory which comprises the resource is arranged.

### -field Flags

A bitwise-OR-ed value of [**D3D12_RESOURCE_FLAGS**](/windows/win32/api/d3d12/ne-d3d12-d3d12_resource_flags) flags which describe the ways the resource is to be used.

### -field InitialResourceState

A bitwise-OR-ed value of [**D3D12_RESOURCE_STATES**](/windows/win32/api/d3d12/ne-d3d12-d3d12_resource_states) values that describe the initial resource state.

### -field pRowMajorLayout

When **Layout** is D3D12DDI_TL_ROW_MAJOR and **pRowMajorLayout** is non-null, then ***pRowMajorLayout** points to a [**D3D12DDIARG_ROW_MAJOR_RESOURCE_LAYOUT**](ns-d3d12umddi-d3d12ddiarg_row_major_resource_layout.md) structure that specifies the layout of the resource.

### -field SamplerFeedbackDesc

Deprecated. Use [**D3D12DDIARG_CREATERESOURCE_0075**](ns-d3d12umddi-d3d12ddiarg_createresource_0075.md) for sampler feedback.

## -remarks

## -see-also

[**D3D12DDIARG_CREATERESOURCE_0088**](ns-d3d12umddi-d3d12ddiarg_createresource_0088.md)
