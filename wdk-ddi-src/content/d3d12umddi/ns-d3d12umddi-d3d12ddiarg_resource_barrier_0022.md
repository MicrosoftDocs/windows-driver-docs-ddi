---
UID: NS:d3d12umddi.D3D12DDIARG_RESOURCE_BARRIER_0022
title: D3D12DDIARG_RESOURCE_BARRIER_0022 (d3d12umddi.h)
description: Describes a resource barrier.
old-location: display\d3d12ddiarg_resource_barrier_0022.htm
ms.date: 05/24/2022
keywords: ["D3D12DDIARG_RESOURCE_BARRIER_0022 structure"]
ms.keywords: D3D12DDIARG_RESOURCE_BARRIER_0022, D3D12DDIARG_RESOURCE_BARRIER_0022 structure [Display Devices], d3d12umddi/D3D12DDIARG_RESOURCE_BARRIER_0022, display.d3d12ddiarg_resource_barrier_0022
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
req.typenames: D3D12DDIARG_RESOURCE_BARRIER_0022
f1_keywords:
 - D3D12DDIARG_RESOURCE_BARRIER_0022
 - d3d12umddi/D3D12DDIARG_RESOURCE_BARRIER_0022
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDIARG_RESOURCE_BARRIER_0022
---

# D3D12DDIARG_RESOURCE_BARRIER_0022 structure

## -description

The **D3D12DDIARG_RESOURCE_BARRIER_0022** structure contains the resource barrier parameters for the [**PFND3D12DDI_RESOURCEBARRIER_0022**](nc-d3d12umddi-pfnd3d12ddi_resourcebarrier_0022.md).

## -struct-fields

### -field Type

The type of resource barrier as a [**D3D12DDI_RESOURCE_BARRIER_TYPE**](ne-d3d12umddi-d3d12ddi_resource_barrier_type.md) value. This member determines which barrier type to use in the union below.

### -field Flags

A barrier flag as a [**D3D12DDI_RESOURCE_BARRIER_FLAGS**](ne-d3d12umddi-d3d12ddi_resource_barrier_flags.md) value.

### -field Transition

A [**D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003**](ns-d3d12umddi-d3d12ddi_resource_transition_barrier_0003.md) structure that describes the transition of subresources between different usages. This structure's members specify the before and after usages of the subresources.

### -field Ranged

A [**D3D12DDI_RESOURCE_RANGED_BARRIER_0022**](ns-d3d12umddi-d3d12ddi_resource_ranged_barrier_0022.md) structure that describes a ranged barrier.

### -field UAV

A [**D3D12DDI_RESOURCE_UAV_BARRIER**](ns-d3d12umddi-d3d12ddi_resource_uav_barrier.md) structure that describes a resource in which all UAV accesses (reads or writes) must complete before any future UAV accesses (read or write) can begin.

## -see-also

[**PFND3D12DDI_RESOURCEBARRIER_0022**](nc-d3d12umddi-pfnd3d12ddi_resourcebarrier_0022.md)
