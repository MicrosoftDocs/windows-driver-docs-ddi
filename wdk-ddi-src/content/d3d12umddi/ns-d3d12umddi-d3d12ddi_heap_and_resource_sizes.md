---
UID: NS:d3d12umddi.D3D12DDI_HEAP_AND_RESOURCE_SIZES
tech.root: display
title: D3D12DDI_HEAP_AND_RESOURCE_SIZES
ms.date: 02/28/2023
targetos: Windows
description: Learn more about the D3D12DDI_HEAP_AND_RESOURCE_SIZES structure.
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
req.typenames: D3D12DDI_HEAP_AND_RESOURCE_SIZES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_HEAP_AND_RESOURCE_SIZES
f1_keywords:
 - D3D12DDI_HEAP_AND_RESOURCE_SIZES
 - d3d12umddi/D3D12DDI_HEAP_AND_RESOURCE_SIZES
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_HEAP_AND_RESOURCE_SIZES
---

## -description

**D3D12DDI_HEAP_AND_RESOURCE_SIZES** specifies the sizes of a private heap and resource.

## -struct-fields

### -field Heap

Number of bytes required to allocate the heap described in a call to a driver's [*PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0088**](nc-d3d12umddi-pfnd3d12ddi_calcprivateheapandresourcesizes_0088.md) callback function.

### -field Resource

Number of bytes required to allocate the heap described in a call to a driver's [*PFND3D12DDI_CALCPRIVATEHEAPANDRESOURCESIZES_0088**](nc-d3d12umddi-pfnd3d12ddi_calcprivateheapandresourcesizes_0088.md) callback function.
