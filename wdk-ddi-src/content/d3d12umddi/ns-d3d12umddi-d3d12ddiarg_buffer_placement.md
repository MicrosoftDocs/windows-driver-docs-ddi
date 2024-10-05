---
UID: NS:d3d12umddi.D3D12DDIARG_BUFFER_PLACEMENT
tech.root: display
title: D3D12DDIARG_BUFFER_PLACEMENT
ms.date: 10/04/2024
targetos: Windows
description: Learn more about the D3D12DDIARG_BUFFER_PLACEMENT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDIARG_BUFFER_PLACEMENT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_BUFFER_PLACEMENT
f1_keywords:
 - D3D12DDIARG_BUFFER_PLACEMENT
 - d3d12umddi/D3D12DDIARG_BUFFER_PLACEMENT
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDIARG_BUFFER_PLACEMENT
---

## -description

The **D3D12DDIARG_BUFFER_PLACEMENT** structure specifies the GPU-side virtual address that a resource should have.

## -struct-fields

### -field BaseAddress

Union whose members are ways to describe the base address for a region of memory.

### -field BaseAddress.UMD

A **D3D12DDIARG_HRESOURCE_PLACEMENT** structure that describes a base address with a UMD handle to an existing resource, and a byte offset within that resource.

## -see-also

[**D3D12DDIARG_CREATERESOURCE_0088**](ns-d3d12umddi-d3d12ddiarg_createresource_0088.md)