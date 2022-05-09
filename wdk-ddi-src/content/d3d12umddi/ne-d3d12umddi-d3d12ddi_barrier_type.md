---
UID: NE:d3d12umddi.D3D12DDI_BARRIER_TYPE
tech.root: display
title: D3D12DDI_BARRIER_TYPE
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the D3D12DDI_BARRIER_TYPE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_BARRIER_TYPE
f1_keywords:
 - D3D12DDI_BARRIER_TYPE
 - d3d12umddi/D3D12DDI_BARRIER_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_BARRIER_TYPE
---

## -description

A **D3D12DDI_BARRIER_TYPE** enumeration value indicates the type of resource barrier.

## -enum-fields

### -field D3D12DDI_BARRIER_TYPE_GLOBAL

Indicates a global barrier type. A global barrier applies to all resource memory. Global barriers do not transition texture layouts or force any data decompression.

### -field D3D12DDI_BARRIER_TYPE_TEXTURE

Indicates a texture barrier type. A texture barrier applies to a specific range of texture subresources.

### -field D3D12DDI_BARRIER_TYPE_BUFFER

Indicates a buffer barrier type. A buffer barrier applies to a specific buffer resource.

### -field D3D12DDI_BARRIER_TYPE_RANGED

Indicates a ranged barrier type. A ranged barrier replaces the legacy D3D12DDI_RESOURCE_RANGED_BARRIER_0022.

## -remarks

See [Enhanced Barriers](/windows-hardware/drivers/display/enhanced-barriers) for general information.

## -see-also

[**D3D12DDIARG_BARRIER_0088**](ns-d3d12umddi-d3d12ddiarg_barrier_0088.md)

[**PFND3D12DDI_BARRIER_0088**](nc-d3d12umddi-pfnd3d12ddi_barrier_0088.md)
