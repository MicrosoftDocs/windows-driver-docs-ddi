---
UID: NE:d3d12umddi.D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS
title: D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS (d3d12umddi.h)
description: Defines resource optimization flags.
ms.date: 09/29/2022
keywords: ["D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS enumeration"]
ms.keywords: D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS, D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS
 - d3d12umddi/D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS
dev_langs:
 - c++
---

# D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS enumeration

## -description

The **D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS** enumeration is a bitwise OR value that defines a resource's optimization flags.

## -enum-fields

### -field D3D12DDI_RESOURCE_OPTIMIZATION_FLAG_NONE:0x0

No options are specified.

### -field D3D12DDI_RESOURCE_OPTIMIZATION_FLAG_SHADER_RESOURCE:0x1

Perform shader resource optimizations.

### -field D3D12DDI_RESOURCE_OPTIMIZATION_FLAG_UNORDERED_ACCESS:0x2

Perform unordered access view optimizations.

### -field D3D12DDI_RESOURCE_OPTIMIZATION_FLAG_PRIMARY:0x4

Perform primary heap optimizations.

### -field D3D12DDI_RESOURCE_OPTIMIZATION_FLAG_DETERMINISTIC:0x8

Perform deterministic optimizations.

## -see-also

[**D3D12_RESOURCE_FLAGS**](/windows/win32/api/d3d12/ne-d3d12-d3d12_resource_flags)

[**PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0088**](nc-d3d12umddi-pfnd3d12ddi_checkresourceallocationinfo_0088.md)
