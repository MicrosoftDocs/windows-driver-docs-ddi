---
UID: NS:d3d12umddi.D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041
title: D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041 (d3d12umddi.h)
description: Defines the memory architecture capabilities.
ms.date: 10/19/2018
keywords: ["D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041 structure"]
ms.keywords: D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041, D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041
targetos: Windows
tech.root: display
f1_keywords:
 - D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041
 - d3d12umddi/D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041
product:
 - Windows
---

# D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041 structure


## -description

Defines the memory architecture capabilities.

## -struct-fields

### -field UMA

The Unified Memory Architecture (UMA).

### -field IOCoherent

This field indicates that the memory page is I/O coherent.

### -field CacheCoherent

When set, this field indicates that the memory page is cache coherent.

### -field HeapSerializationTier

Specifies the heap serialization tier.

### -field ResourceSerializationTier

Specifies the resource serialization tier.

