---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKFORMATSUPPORT
title: PFND3D12DDI_CHECKFORMATSUPPORT (d3d12umddi.h)
description: Implemented by the client driver to check the format support.
ms.assetid: b05a2e1a-5839-4a5e-83c5-67bfd41287b0
ms.date: 10/19/2018
ms.topic: callback
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
topic_type:
- apiref
api_type:
- UserDefined
api_location:
- d3d12umddi.h
api_name:
- PFND3D12DDI_CHECKFORMATSUPPORT
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CHECKFORMATSUPPORT callback function

## -description

Implemented by the client driver to check the format support.

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

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).

### -param DXGI_FORMAT

A DXGI_FORMAT.

### -param *

Pointer to a UINT.

## -returns

Returns VOID.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3D12DDI_DeVICE_FUNCS_CORE_0010](C:\drivers\wdk-ddi\wdk-ddi-src\content\d3d12umddi\ns-d3d12umddi-d3d12ddi_device_funcs_core_0010.md).

