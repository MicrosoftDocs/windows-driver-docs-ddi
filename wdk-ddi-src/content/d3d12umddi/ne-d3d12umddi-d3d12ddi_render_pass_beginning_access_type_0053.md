---
UID: NE:d3d12umddi.D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053
title: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053 (d3d12umddi.h)
description: Declares the type of resource access to begin a Render Pass.
ms.assetid: 2db80a0c-b883-4e13-9763-37b135923a26
ms.date: 10/19/2018
ms.topic: enum
f1_keywords:
 - "d3d12umddi/D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053"
ms.keywords: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053, D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053, 
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053 enumeration

## -description

Declares the type of resource access for the call to [PFND3D12DDI_BEGIN_RENDER_PASS_0053](nc-d3d12umddi-pfnd3d12ddi_begin_render_pass_0053.md).

## -enum-fields

### -field D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053_DISCARD

Indicates that the application does not have any dependency on the prior contents of the resource. 

A given implementation may return the previously-written contents, or it may return uninitialized data. However, reading from the resource must not produce a GPU hang, and the 'read' may only return undefined data in the worst case.
A read is defined as a traditional:

* UAV (Unordered Access View)
* SRV (Shader Resource View)
* CBV (Constant Buffer View)
* VBV (Vertex Buffer View)
* IBV (Index Buffer View)
* IndirectArg binding/read
* blend/depth-testing-induced read

### -field D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_PRESERVE

Indicates that the application has a dependency on the prior contents of the resource, and the contents must be loaded from main memory.

### -field D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR

Indicates that the application has a dependency on the resource being cleared to a specific (app-provided) color. 

> [!NOTE]
> This clear occurs whether or not the resource has interacted with anything beyond the Render Pass.

The API will allow the application to specify the clear values in the call to [PFND3D12DDI_BEGIN_RENDER_PASS_0053](nc-d3d12umddi-pfnd3d12ddi_begin_render_pass_0053.md), via the [D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS_0053](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_clear_parameters_0053.md) structure.


### -field D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_NO_ACCESS

Indicates that the resource will not be read from or written to during the Render Pass. This value also indicates whether the depth/stencil plane for a DSV (Data Source View) was not accessed.

> [!IMPORTANT]
> This value must be paired with the *D3D12DDI_RENDER_PASS_ENDING_ACCESS_NO_ACCESS* value in [D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053](ne-d3d12umddi-d3d12ddi_render_pass_ending_access_type_0053.md).



## -remarks

## -see-also
