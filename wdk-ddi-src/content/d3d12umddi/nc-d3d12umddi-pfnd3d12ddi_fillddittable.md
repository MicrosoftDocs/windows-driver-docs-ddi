---
UID: NC:d3d12umddi.PFND3D12DDI_FILLDDITTABLE
title: PFND3D12DDI_FILLDDITTABLE (d3d12umddi.h)
description: Implemented by the client driver to retrieve the D3D12DDI_DEVICE_FUNCS_VIDEO structure.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_FILLDDITTABLE callback function"]
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
 - PFND3D12DDI_FILLDDITTABLE
 - d3d12umddi/PFND3D12DDI_FILLDDITTABLE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_FILLDDITTABLE
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_FILLDDITTABLE callback function


## -description

Implemented by the client driver to retrieve the [D3D12DDI_DEVICE_FUNCS_VIDEO](ns-d3d12umddi-d3d12ddi_device_funcs_video_0033.md) structure.

## -parameters

### -param unnamedParam1

Adapter handle.

### -param unnamedParam2

Table type.

### -param unnamedParam3

Void.

### -param unnamedParam4

Size of the table.

### -param unnamedParam5

### -param unnamedParam6

Table handle.

## -returns

Returns an HRESULT value.

## -prototype

```cpp
//Declaration

PFND3D12DDI_FILLDDITTABLE Pfnd3d12ddiFillddittable;

// Definition

HRESULT Pfnd3d12ddiFillddittable
(
	 D3D12DDI_HADAPTER
	 D3D12DDI_TABLE_TYPE
	VOID *
	 SIZE_T
	 UINT
	 D3D12DDI_HRTTABLE
)
{...}

PFND3D12DDI_FILLDDITTABLE


```

