---
UID: NE:d3d12umddi.D3D12DDI_BARRIER_TYPE
tech.root: display
title: D3D12DDI_BARRIER_TYPE
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the D3D12DDI_BARRIER_TYPE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
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

The barrier is a global barrier. A global barrier applies to all resource memory. Global barriers do not transition texture layouts or force any data decompression.

### -field D3D12DDI_BARRIER_TYPE_TEXTURE

The barrier is a texture barrier. A texture barrier applies to a specific range of texture subresources.

### -field D3D12DDI_BARRIER_TYPE_BUFFER

The barrier is a buffer barrier. A buffer barrier applies to a specific buffer resource.

### -field D3D12DDI_BARRIER_TYPE_RANGED

The buffer is a ranged barrier. A ranged barrier replaces the legacy [**D3D12DDI_RESOURCE_RANGED_BARRIER_0022**](nc-d3d12umddi-pfnd3d12ddi_resourcebarrier_0022.md).

## -remarks

See [Enhanced Barriers](/windows-hardware/drivers/display/enhanced-barriers) for general information.

## -see-also

[**D3D12DDIARG_BARRIER_0088**](ns-d3d12umddi-d3d12ddiarg_barrier_0088.md)

[**PFND3D12DDI_BARRIER_0088**](nc-d3d12umddi-pfnd3d12ddi_barrier_0088.md)
