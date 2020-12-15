---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATESCHEDULINGGROUPSIZE_0050
title: PFND3D12DDI_CALCPRIVATESCHEDULINGGROUPSIZE_0050 (d3d12umddi.h)
description: The pfnCalcPrivateSchedulingGroupSize callback function returns the size of the hardware scheduling group.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALCPRIVATESCHEDULINGGROUPSIZE_0050 callback function"]
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
 - PFND3D12DDI_CALCPRIVATESCHEDULINGGROUPSIZE_0050
 - d3d12umddi/PFND3D12DDI_CALCPRIVATESCHEDULINGGROUPSIZE_0050
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATESCHEDULINGGROUPSIZE_0050
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALCPRIVATESCHEDULINGGROUPSIZE_0050 callback function


## -description

The **pfnCalcPrivateSchedulingGroupSize** callback function returns the size of the hardware scheduling group.

## -parameters

### -param Arg1

An hDevice that represents a handle to the display device (graphics context).

### -param Arg2

Pointer to a [D3D12DDIARG_CREATESCHEDULINGGROUP_0050](ns-d3d12umddi-d3d12ddiarg_createschedulinggroup_0050.md) structure that represents arguments needed to create a hardware scheduling group.

## -returns

Returns SIZE_T that represents the size.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATESCHEDULINGGROUPSIZE_0050 Pfnd3d12ddiCalcprivateschedulinggroupsize0050; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivateschedulinggroupsize0050 
(
	D3D12DDI_HDEVICE Arg1
	CONST D3D12DDIARG_CREATESCHEDULINGGROUP_0050 *
)
{...}

```

## -remarks

## -see-also

