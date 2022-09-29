---
UID: NS:d3d12umddi.D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088
tech.root: display
title: D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088 structure.
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
req.typenames: D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088
f1_keywords:
 - D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088
 - d3d12umddi/D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088
---

## -description

The **D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088** structure specifies the range of subresources being transitioned.

## -struct-fields

### -field IndexOrFirstMipLevel

If **NumMipLevels** is zero, **IndexOrFirstMipLevel** specifies a subresource index. A subresource index of 0xffffffff can be used to specify all subresources.

If **NumMipLevels** is not zero, **IndexOrFirstMipLevel** identifies the first mip level in the range.

### -field NumMipLevels

The number of mip levels in the range, or zero to indicate **IndexOrFirstMipLevel** is a subresource index.

### -field FirstArraySlice

Index of the first array slice in the range. **FirstArraySlice** is ignored if **NumMipLevels** is zero.

### -field NumArraySlices

Number of array slices in the range. **NumArraySlices** is ignored if **NumMipLevels** is zero.

### -field FirstPlane

The first plane slice in the range. **FirstPlane** is ignored if **NumMipLevels** is zero.

### -field NumPlanes

The number of plane slices in the range. **NumPlanes** is ignored if **NumMipLevels** is zero.

## -remarks

The **D3D12DDI_BARRIER_SUBRESOURCE_RANGE_0088** structure allows developers to transition a range of subresources such as a full mip-chain for a given texture array or a single mip-level for all array slices. The Enhanced Barriers feature allows developers to transition logically-adjacent ranges of subresources using this structure.

See [Enhanced Barriers](/windows-hardware/drivers/display/enhanced-barriers) for general information.

## -see-also

[**D3D12DDI_RANGED_BARRIER_0088**](ns-d3d12umddi-d3d12ddi_ranged_barrier_0088.md)

[**D3D12DDI_TEXTURE_BARRIER_0088**](ns-d3d12umddi-d3d12ddi_texture_barrier_0088.md)