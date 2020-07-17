---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROY_STATE_OBJECT_0054
title: PFND3D12DDI_DESTROY_STATE_OBJECT_0054 (d3d12umddi.h)
description: Destroys the state object.
ms.assetid: 73822e25-6b9a-4593-aaa9-13c375b8e4c1
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_DESTROY_STATE_OBJECT_0054 callback function"]
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_DESTROY_STATE_OBJECT_0054"
 - "PFND3D12DDI_DESTROY_STATE_OBJECT_0054"
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
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
- PFND3D12DDI_DESTROY_STATE_OBJECT_0054
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# PFND3D12DDI_DESTROY_STATE_OBJECT_0054 callback function

## -description

Destroys the state object.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROY_STATE_OBJECT_0054 Pfnd3d12ddiDestroyStateObject0054; 

// Definition

VOID Pfnd3d12ddiDestroyStateObject0054 
(
	D3D12DDI_HDEVICE Arg1
	D3D12DDI_HSTATEOBJECT_0054 Arg2
)
{...}

```

## -parameters

### -param Arg1

A handle to the device.

### -param Arg2

A handle to the state object to destroy.

## -remarks



## -see-also
