---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0050
title: PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0050 (d3d12umddi.h)
description: The PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0050 callback function is used to calculate the size of a private command queue.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0050 callback function"]
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
 - PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0050
 - d3d12umddi/PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0050
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0050
dev_langs:
 - c++
---

# PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0050 callback function


## -description

The PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0050 callback function is used to calculate the size of a private command queue.

## -parameters

### -param unnamedParam1

The handle of a device.

### -param unnamedParam2

*_In_ CreateCommandQueue*

Pointer to a [D3D12DDIARG_CREATECOMMANDQUEUE_0050](ns-d3d12umddi-d3d12ddiarg_createcommandqueue_0050.md) structure used to create a command queue.

## -returns

Returns SIZE_T that represents the size of the queue.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0050 Pfnd3d12ddiCalcprivatecommandqueuesize0050; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivatecommandqueuesize0050 
(
	D3D12DDI_HDEVICE Arg1
	CONST D3D12DDIARG_CREATECOMMANDQUEUE_0050 *
)
{...}

```

## -remarks

Access this callback function by using a device functions core structure, such as the [D3D12DDI_DEVICE_FUNCS_CORE_0050](ns-d3d12umddi-d3d12ddi_device_funcs_core_0050.md) structure.

## -see-also

