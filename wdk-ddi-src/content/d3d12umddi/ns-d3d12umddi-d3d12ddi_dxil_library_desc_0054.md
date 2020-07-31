---
UID: NS:d3d12umddi.D3D12DDI_DXIL_LIBRARY_DESC_0054
title: D3D12DDI_DXIL_LIBRARY_DESC_0054 (d3d12umddi.h)
description: Describes the DXIL (DirectX Intermediate Language) library.
ms.assetid: d7d1d64d-749e-4d97-a98c-6b6fc7dcfd7f
ms.date: 10/19/2018
keywords: ["D3D12DDI_DXIL_LIBRARY_DESC_0054 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_DXIL_LIBRARY_DESC_0054"
 - "D3D12DDI_DXIL_LIBRARY_DESC_0054"
ms.keywords: D3D12DDI_DXIL_LIBRARY_DESC_0054, D3D12DDI_DXIL_LIBRARY_DESC_0054, 
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
req.typenames: D3D12DDI_DXIL_LIBRARY_DESC_0054
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_DXIL_LIBRARY_DESC_0054
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_DXIL_LIBRARY_DESC_0054 structure

## -description

Describes the DXIL (DirectX Intermediate Language) library.

## -struct-fields

### -field pDXILLibrary

Pointer to a DXIL library.

### -field NumExports

Optional. The number of exports in the DXIL library. If 0, all exports in the library/collection will be surfaced.

### -field pExports
 
Pointer to an array of [D3D12DDI_EXPORT_DESC_0054](ns-d3d12umddi-d3d12ddi_export_desc_0054.md).

## -remarks

If there are multiple explicit subject associations with different subobject definitions that map to a given shader export, this is a conflict.  If a conflict is discovered during DXIL library creation, library creation will fail. Otherwise if a conflict is discovered during state object creation, that fails.

## -see-also
