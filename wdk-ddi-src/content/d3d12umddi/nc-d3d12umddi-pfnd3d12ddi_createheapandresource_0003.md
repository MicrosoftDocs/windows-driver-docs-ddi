---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEHEAPANDRESOURCE_0003
title: PFND3D12DDI_CREATEHEAPANDRESOURCE_0003 (d3d12umddi.h)
description: The PFND3D12DDI_CREATEHEAPANDRESOURCE_0003 callback function simultaneously creates a heap and resource.
ms.date: 02/28/2023
keywords: ["PFND3D12DDI_CREATEHEAPANDRESOURCE_0003 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFND3D12DDI_CREATEHEAPANDRESOURCE_0003
 - d3d12umddi/PFND3D12DDI_CREATEHEAPANDRESOURCE_0003
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEHEAPANDRESOURCE_0003
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATEHEAPANDRESOURCE_0003 callback function

## -description

A user-mode display driver's **PFND3D12DDI_CREATEHEAPANDRESOURCE_0003** function simultaneously creates a heap and resource.

## -parameters

### -param unnamedParam1  

A **D3D12DDI_HDEVICE** handle to the display device (graphics context).

### -param unnamedParam2

A [**D3D12DDIARG_CREATEHEAP_0001**](ns-d3d12umddi-d3d12ddiarg_createheap_0001.md) structure containing the arguments used to create a heap.

### -param unnamedParam3

A **D3D12DDI_HHEAP** handle to a heap.

### -param unnamedParam4

The **D3D12DDI_HRTRESOURCE** handle of the resource for the driver to use when it calls back into the runtime.

### -param unnamedParam5

Pointer to a [**D3D12DDIARG_CREATERESOURCE_0003**](ns-d3d12umddi-d3d12ddiarg_createresource_0003.md) structure containing the arguments used to create a resource.

### -param unnamedParam6

Pointer to a [**D3D12DDI_CLEAR_VALUES**](ns-d3d12umddi-d3d12ddi_clear_values.md) structure with values used to optimize clear operations for the resource.

### -param unnamedParam7

The **D3D12DDI_HRESOURCE** handle to the hardware resource.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.
