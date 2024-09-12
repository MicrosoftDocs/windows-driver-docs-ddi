---
UID: NS:d3d12umddi.D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053
title: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053 (d3d12umddi.h)
description: Learn more about the D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053 structure.
ms.date: 07/02/2024
keywords: ["D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053 structure"]
ms.keywords: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053, D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053
 - d3d12umddi/D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053
dev_langs:
 - c++
---

# D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053 structure

## -description

The **D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_0053** structure specifies the resources needed to start a render pass.

## -struct-fields

### -field Type

A [**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053**](ne-d3d12umddi-d3d12ddi_render_pass_beginning_access_type_0053.md) value that specifies the type of access being requested. This value determines which union field is used.

### -field Clear

A [**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_CLEAR_PARAMETERS_0053**](ns-d3d12umddi-d3d12ddi_render_pass_beginning_access_clear_parameters_0053.md) structure with parameters for a clear operation.

### -field PreserveLocal

A **D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_PRESERVE_LOCAL_PARAMETERS_0101** structure with parameters for a local data preserve operation.

## -remarks

## -see-also

[**PFND3D12DDI_BEGIN_RENDER_PASS_0053**](nc-d3d12umddi-pfnd3d12ddi_begin_render_pass_0053.md)