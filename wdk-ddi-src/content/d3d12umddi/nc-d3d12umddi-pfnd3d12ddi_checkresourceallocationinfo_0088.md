---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0088
tech.root: display
title: PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0088
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0088 callback function.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0088
f1_keywords:
 - PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0088
 - d3d12umddi/PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0088
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0088
---

## -description

The **PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0088** callback function supports checking resource allocation information.

## -parameters

### -param unnamedParam1

[in] A handle to the display device (graphics context).

### -param unnamedParam2

[in] Pointer to a [**D3D12DDIARG_CREATERESOURCE_0088**](ns-d3d12umddi-d3d12ddiarg_createresource_0088.md) structure.

### -param unnamedParam3

A [**D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS**](ne-d3d12umddi-d3d12ddi_resource_optimization_flags.md) value that specifies the resource optimization flags.

### -param AlignmentRestriction

A resource alignment restriction value.

### -param VisibleNodeMask

For a multi-adapter operation, this value indicates the set of nodes where the resource is visible. Passing zero is equivalent to passing one, in order to simplify the usage of single-GPU adapters.

### -param unnamedParam6

Pointer to a [**D3D12DDI_RESOURCE_ALLOCATION_INFO_0022**](ns-d3d12umddi-d3d12ddi_resource_allocation_info_0022.md) structure containing information for resource allocation.

## -remarks

This callback function is part of a two step process of resource creation. This function determines the sizes and alignments of the resource data, additional data header, and additional data is determined, along with the texture layout. When the resource description is passed into this function, the layout of the resource description may be set to _UNDEFINED. This allows the driver to choose any texture layout. When the layout of the resource description is **STANDARD_SWIZZLE** or **ROW_MAJOR**, the driver must return out the corresponding value as its choice.

This callback function is accessed by using the [**D3D12DDI_DEVICE_FUNCS_CORE_0088**](ns-d3d12umddi-d3d12ddi_device_funcs_core_0088.md) structure.

## -see-also

[**D3D12DDI_DEVICE_FUNCS_CORE_0088**](ns-d3d12umddi-d3d12ddi_device_funcs_core_0088.md)

[**PFND3D12DDI_CREATEHEAPANDRESOURCE_0088**](nc-d3d12umddi-pfnd3d12ddi_createheapandresource_0088.md)
