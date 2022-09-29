---
UID: NS:d3d12umddi.D3D12DDIARG_CREATERESOURCE_0088
tech.root: display
title: D3D12DDIARG_CREATERESOURCE_0088
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the D3D12DDIARG_CREATERESOURCE_0088 structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDIARG_CREATERESOURCE_0088
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATERESOURCE_0088
f1_keywords:
 - D3D12DDIARG_CREATERESOURCE_0088
 - d3d12umddi/D3D12DDIARG_CREATERESOURCE_0088
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDIARG_CREATERESOURCE_0088
---

## -description

The **D3D12DDIARG_CREATERESOURCE_0088** structure contains the information needed to create or calculate the size of a resource.

## -struct-fields

### -field ReuseBufferGPUVA

A [**D3D12DDIARG_BUFFER_PLACEMENT**](ns-d3d12umddi-d3d12ddiarg_buffer_placement.md) structure that specifies the GPU-side virtual address that the resource should have, if it does not need a new one assigned.

### -field ResourceType

A [**D3D12DDI_RESOURCE_TYPE**](ne-d3d12umddi-d3d12ddi_resource_type.md) value that identifies the type of this resource.

### -field Width

The width of the resource. This is in texels, if the resource is a texture, or bytes if the resource is a buffer.

### -field Height

The height of the resource. This applies to two-dimensional and three-dimensional textures.

### -field DepthOrArraySize

The depth, or array size of the resource used when the resource is three-dimensional, or arrayed respectively.

### -field MipLevels

The number of mip levels the resource has.

### -field Format

Specifies how the resource's data is to be interpreted, using a [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) enumeration value.

### -field SampleDesc

A [**DXGI_SAMPLE_DESC**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_sample_desc) structure that describes the multi-sampling parameters for the resource.

### -field Layout

A [**D3D12DDI_TEXTURE_LAYOUT**](ne-d3d12umddi-d3d12ddi_texture_layout.md) value that specifies details related to how the memory which comprises the resource is arranged.

### -field Flags

A [**D3D12DDI_RESOURCE_FLAGS_0003**](ne-d3d12umddi-d3d12ddi_resource_flags_0003.md) value with bitwise-OR'd flags that describe the ways the resource is to be used.

### -field InitialBarrierLayout

A [**D3D12DDI_BARRIER_LAYOUT**](ne-d3d12umddi-d3d12ddi_barrier_layout.md) value that specifies the initial layout of the resource.

### -field pRowMajorLayout

A [**D3D12DDIARG_ROW_MAJOR_RESOURCE_LAYOUT**]( ns-d3d12umddi-d3d12ddiarg_row_major_resource_layout.md) structure that describes the layout of a row-major resource. When **Layout** is **D3D12DDI_TL_ROW_MAJOR** and **pRowMajorLayout** is non-null, then ***pRowMajorLayout** specifies the layout of the resource.

### -field SamplerFeedbackMipRegion

A [**D3D12DDI_MIP_REGION_0075**](ns-d3d12umddi-d3d12ddi_mip_region_0075.md) structure specifying the size of a mip region.

### -field NumCastableFormats

The number of elements that **pCastableFormats** points to.

### -field pCastableFormats

Pointer to a contiguous array of [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) values that this resource can be cast to.

## -see-also

[**PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0088**](nc-d3d12umddi-pfnd3d12ddi_calcprivateheapandresourcesizes_0088.md)

[**PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0088**](nc-d3d12umddi-pfnd3d12ddi_checkresourceallocationinfo_0088.md)

[**PFND3D12DDI_CREATEHEAPANDRESOURCE_0088**](nc-d3d12umddi-pfnd3d12ddi_createheapandresource_0088.md)
