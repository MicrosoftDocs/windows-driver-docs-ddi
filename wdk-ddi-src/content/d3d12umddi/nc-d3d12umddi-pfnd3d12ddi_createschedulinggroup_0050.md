---
UID: NC:d3d12umddi.PFND3D12DDI_CREATESCHEDULINGGROUP_0050
title: PFND3D12DDI_CREATESCHEDULINGGROUP_0050 (d3d12umddi.h)
description: Creates a scheduling group.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CREATESCHEDULINGGROUP_0050 callback function"]
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFND3D12DDI_CREATESCHEDULINGGROUP_0050
 - d3d12umddi/PFND3D12DDI_CREATESCHEDULINGGROUP_0050
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATESCHEDULINGGROUP_0050
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CREATESCHEDULINGGROUP_0050 callback function


## -description

Creates a scheduling group.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

Pointer to a [D3D12DDIARG_CREATESCHEDULINGGROUP_0050](ns-d3d12umddi-d3d12ddiarg_createschedulinggroup_0050.md) structure that contains arguments to create a scheduling group.

### -param Arg3

A D3D12DDI_HRTSCHEDULINGGROUP_0050 runtime handle type that represents the contexts associated with a hardware scheduling group.

### -param Arg4

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATESCHEDULINGGROUP_0050 Pfnd3d12ddiCreateschedulinggroup0050; 

// Definition

HRESULT Pfnd3d12ddiCreateschedulinggroup0050 
(
	D3D12DDI_HDEVICE Arg1
	CONST D3D12DDIARG_CREATESCHEDULINGGROUP_0050 *
	D3D12DDI_HSCHEDULINGGROUP_0050 Arg2
	D3D12DDI_HRTSCHEDULINGGROUP_0050 Arg3
)
{...}

```

## -remarks

A scheduling group is a driver object that the runtime will create, and which must have at least one 3D/compute context created during its construction. The runtime will allow multiple contexts to be constructed. Once the driver returns from CreateSchedulingGroup, no more contexts may be added.

The scheduling group should contain all contexts which target shared hardware or resources that will be leveraged by any child command queues. It does not need to contain all contexts for all child queues.

## -see-also

