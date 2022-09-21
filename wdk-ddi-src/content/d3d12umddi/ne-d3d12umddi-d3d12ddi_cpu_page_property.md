---
UID: NE:d3d12umddi.D3D12DDI_CPU_PAGE_PROPERTY
tech.root: display
title: D3D12DDI_CPU_PAGE_PROPERTY
ms.date: 09/22/2022
targetos: Windows
description: Learn more about the D3D12DDI_CPU_PAGE_PROPERTY enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
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
 - D3D12DDI_CPU_PAGE_PROPERTY
f1_keywords:
 - D3D12DDI_CPU_PAGE_PROPERTY
 - d3d12umddi/D3D12DDI_CPU_PAGE_PROPERTY
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_CPU_PAGE_PROPERTY
---

## -description

A **D3D12DDI_CPU_PAGE_PROPERTY** value specifies the CPU page properties for a heap.

## -enum-fields

### -field D3D12DDI_CPU_PAGE_PROPERTY_NOT_AVAILABLE:0

The CPU cannot access the heap; therefore no page properties are available.

### -field D3D12DDI_CPU_PAGE_PROPERTY_WRITE_COMBINE:1

The CPU page property is write-combined.

### -field D3D12DDI_CPU_PAGE_PROPERTY_WRITE_BACK:2

The CPU page property is write-back.

## -see-also

[**D3D12DDIARG_CREATEHEAP_0001**](ns-d3d12umddi-d3d12ddiarg_createheap_0001.md)
