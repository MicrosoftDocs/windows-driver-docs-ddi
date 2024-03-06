---
UID: NE:d3d12umddi.D3D12DDI_META_COMMAND_PARAMETER_TYPE
title: D3D12DDI_META_COMMAND_PARAMETER_TYPE (d3d12umddi.h)
description: Indicates the meta-command type.
ms.date: 10/19/2018
keywords: ["D3D12DDI_META_COMMAND_PARAMETER_TYPE enumeration"]
ms.keywords: D3D12DDI_META_COMMAND_PARAMETER_TYPE, D3D12DDI_META_COMMAND_PARAMETER_TYPE,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_META_COMMAND_PARAMETER_TYPE
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_META_COMMAND_PARAMETER_TYPE
 - d3d12umddi/D3D12DDI_META_COMMAND_PARAMETER_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_META_COMMAND_PARAMETER_TYPE
dev_langs:
 - c++
---

# D3D12DDI_META_COMMAND_PARAMETER_TYPE enumeration

## -description

A **D3D12DDI_META_COMMAND_PARAMETER_TYPE** value indicates the meta-command type.

## -enum-fields

### -field D3D12DDI_META_COMMAND_PARAMETER_TYPE_FLOAT:0

The parameter type is float.

### -field D3D12DDI_META_COMMAND_PARAMETER_TYPE_UINT64:1

The parameter type is UINT64.

### -field D3D12DDI_META_COMMAND_PARAMETER_TYPE_GPU_VIRTUAL_ADDRESS:2

GPU virtual address.

### -field D3D12DDI_META_COMMAND_PARAMETER_TYPE_CPU_DESCRIPTOR_HANDLE_HEAP_TYPE_CBV_SRV_UAV:3

CPU descriptor handle heap type CBV (constant buffer view), SRV (shader resource view), or UAV (unordered access view).

### -field D3D12DDI_META_COMMAND_PARAMETER_TYPE_GPU_DESCRIPTOR_HANDLE_HEAP_TYPE_CBV_SRV_UAV:4

GPU descriptor handle heap type CBV (constant buffer view), SRV (shader resource view), or UAV (unordered access view).

## -remarks

## -see-also

[**D3D12DDIARG_META_COMMAND_PARAMETER_DESC**](ns-d3d12umddi-d3d12ddiarg_meta_command_parameter_desc.md)
