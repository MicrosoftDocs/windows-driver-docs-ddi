---
UID: NE:d3d12umddi.D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053
title: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053 (d3d12umddi.h)
description: The call to begin a render pass uses the D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053 enumeration to specify the type of resource access.
ms.date: 03/28/2025
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053
 - d3d12umddi/D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053
dev_langs:
 - c++
---

# D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053 enumeration

## -description

The **D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053** enumeration specifies the type of resource access being requested at the start of a render pass.

## -enum-fields

### -field D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053_DISCARD

Indicates that the application doesn't have any dependency on the prior contents of the resource.

A given driver implementation can return the previously-written contents or uninitialized data. Regardless, reading from the resource must not produce a GPU hang, and the 'read' can only return undefined data in the worst case. A read is defined as a traditional:

* UAV (Unordered Access View)
* SRV (Shader Resource View)
* CBV (Constant Buffer View)
* VBV (Vertex Buffer View)
* IBV (Index Buffer View)
* IndirectArg binding/read
* blend/depth-testing-induced read

### -field D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053_PRESERVE

Indicates that the application has a dependency on the prior contents of the resource, and the contents must be loaded from main memory.

### -field D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053_CLEAR

Indicates that the originating application has a dependency on the resource being cleared to a specific (app-provided) color.

This clear occurs whether or not the resource has interacted with anything beyond the Render Pass.

The clear parameters are specified in the [**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS_0053**](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_clear_parameters_0053.md) structure.

### -field D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053_NO_ACCESS

Indicates that the resource won't be read from or written to during the Render Pass. This value also indicates whether the depth/stencil plane for a DSV (Data Source View) was not accessed.

This value must be paired with the **D3D12DDI_RENDER_PASS_ENDING_ACCESS_NO_ACCESS** value in [**D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053**](ne-d3d12umddi-d3d12ddi_render_pass_ending_access_type_0053.md).

## D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0101_PRESERVE_LOCAL_RENDER

This value signifies that:

* The resource was read or written in the preceding pass, and data from that resource that might be in tile memory can stay there for the current pass.

* The current pass will render to the resource in such a way that processing for a given pixel coordinate will access the same location in the resource that the previous pass accessed.

The driver should reference the[**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_PRESERVE_LOCAL_PARAMETERS_0101**](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_preserve_local_parameters_0101.md) structure for this type.

The end of the previous pass must specify [**D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0101_PRESERVE_LOCAL_RENDER**](ne-d3d12umddi-d3d12ddi_render_pass_ending_access_type_0053.md) and the same **AdditionalWidth**/**AdditionalHeight** parameters.

## D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0101_PRESERVE_LOCAL_SRV

This value signifies that:

* The resource was read or written in the preceding pass, and data from that resource that may be in tile memory can stay there for the current pass.

* The current pass will read from the resource via SRV (shader resource view) binding(s) in the descriptor heap in such a way that processing for a given pixel coordinate will access the same location in the resource that the previous pass accessed.

The driver should reference the[**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0101_PRESERVE_LOCAL_RENDER**](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_preserve_local_parameters_0101.md) structure for this type.

The end of the previous pass must specify [**D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0101_PRESERVE_LOCAL_SRV**](ne-d3d12umddi-d3d12ddi_render_pass_ending_access_type_0053.md) and the same **AdditionalWidth**/**AdditionalHeight** parameters.

## D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0101_PRESERVE_LOCAL_UAV

This value signifies that:

* The resource was read or written in the preceding pass, and data from that resource that may be in tile memory can stay there for the current pass.

* The current pass will read/write the resource via UAV binding(s) in the descriptor heap in such a way that processing for a given pixel coordinate will access the same location in the resource that the previous pass accessed.

The driver should reference the[**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0101_PRESERVE_LOCAL_RENDER**](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_preserve_local_parameters_0101.md) structure for this type.

The end of the previous pass must specify [**D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0101_PRESERVE_LOCAL_UAV**](ne-d3d12umddi-d3d12ddi_render_pass_ending_access_type_0053.md) and the same **AdditionalWidth**/**AdditionalHeight** parameters.

## -remarks

For more information, see [D3D12 Render Passes](/windows-hardware/drivers/display/render-passes).

## -see-also

[**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0101_PRESERVE_LOCAL_RENDER**](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_preserve_local_parameters_0101.md)

[**pfnBeginRenderPass**](nc-d3d12umddi-pfnd3d12ddi_begin_render_pass_0053.md)
