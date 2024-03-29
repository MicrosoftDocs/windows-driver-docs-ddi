---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKFORMATSUPPORT
title: PFND3D12DDI_CHECKFORMATSUPPORT (d3d12umddi.h)
description: Implemented by the client driver to check the format support.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CHECKFORMATSUPPORT callback function"]
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
 - PFND3D12DDI_CHECKFORMATSUPPORT
 - d3d12umddi/PFND3D12DDI_CHECKFORMATSUPPORT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CHECKFORMATSUPPORT
dev_langs:
 - c++
---

# PFND3D12DDI_CHECKFORMATSUPPORT callback function

## -description

Implemented by the client driver to check the format support.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param unnamedParam2

A DXGI_FORMAT.

### -param unnamedParam3

Pointer to a UINT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CHECKFORMATSUPPORT Pfnd3d12ddiCheckformatsupport;

// Definition

VOID Pfnd3d12ddiCheckformatsupport
(
    D3D12DDI_HDEVICE
    DXGI_FORMAT
    UINT *
)
{...}

PFND3D12DDI_CHECKFORMATSUPPORT


```

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3D12DDI_DEVICE_FUNCS_CORE_0010](ns-d3d12umddi-d3d12ddi_device_funcs_core_0010.md).
