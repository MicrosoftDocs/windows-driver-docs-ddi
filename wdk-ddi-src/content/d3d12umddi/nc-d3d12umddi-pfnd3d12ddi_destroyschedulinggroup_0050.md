---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYSCHEDULINGGROUP_0050
title: PFND3D12DDI_DESTROYSCHEDULINGGROUP_0050 (d3d12umddi.h)
description: Destroys a hardware scheduling group.
ms.assetid: 688cd4a2-6775-42e8-8dde-88a0d4d196b6
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_DESTROYSCHEDULINGGROUP_0050"
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
- PFND3D12DDI_DESTROYSCHEDULINGGROUP_0050
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# PFND3D12DDI_DESTROYSCHEDULINGGROUP_0050 callback function

## -description

Destroys a hardware scheduling group.

## -prototype

```cpp
//Declaration

PFND3D12DDI_DESTROYSCHEDULINGGROUP_0050 Pfnd3d12ddiDestroyschedulinggroup0050; 

// Definition

VOID Pfnd3d12ddiDestroyschedulinggroup0050 
(
	D3D12DDI_HDEVICE Arg1
	D3D12DDI_HSCHEDULINGGROUP_0050 Arg2
)
{...}

```

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

A D3D12DDI_HSCHEDULINGGROUP_0050 user mode driver handle type that represents a hardware scheduling group.

## -remarks



## -see-also
