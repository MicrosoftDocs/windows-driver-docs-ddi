---
UID: NS:d3d12umddi.D3D12DDIARG_ROW_MAJOR_RESOURCE_LAYOUT
tech.root: display
title: D3D12DDIARG_ROW_MAJOR_RESOURCE_LAYOUT
ms.date: 09/22/2022
targetos: Windows
description: Learn more about the D3D12DDIARG_ROW_MAJOR_RESOURCE_LAYOUT structure.
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
req.typenames: D3D12DDIARG_ROW_MAJOR_RESOURCE_LAYOUT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_ROW_MAJOR_RESOURCE_LAYOUT
f1_keywords:
 - D3D12DDIARG_ROW_MAJOR_RESOURCE_LAYOUT
 - d3d12umddi/D3D12DDIARG_ROW_MAJOR_RESOURCE_LAYOUT
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDIARG_ROW_MAJOR_RESOURCE_LAYOUT
---

## -description

The **D3D12DDIARG_ROW_MAJOR_RESOURCE_LAYOUT** structure describes the layout of a row-major resource.

## -struct-fields

### -field RowPitch

The length in bytes of the pitch, or width, of one row of the resource.

### -field SlicePitch

The distance in bytes from the beginning of one depth level to the next.
Slice pitch is only used for 3D texture data as it has no meaning for the other resource types.

## -see-also

[**D3D12DDIARG_CREATERESOURCE_0088**](ns-d3d12umddi-d3d12ddiarg_createresource_0088.md)
