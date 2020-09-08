---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0001
title: PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0001 (d3d12umddi.h)
description: The pfnCalcPrivateCommandQueueSize callback function is used to calculate the size of a private command queue.
ms.assetid: d0ff52b6-0e23-4cb9-8da7-4037ee3ec96a
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0001 callback function"]
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
 - PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0001
 - d3d12umddi/PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0001
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0001
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0001 callback function


## -description

The <i>pfnCalcPrivateCommandQueueSize</i> callback function is used to calculate the size of a private command queue.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param Arg2

An argument used to create a command queue.

## -returns

Returns SIZE_T.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0001 Pfnd3d12ddiCalcprivatecommandqueuesize0001; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivatecommandqueuesize0001 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATECOMMANDQUEUE_0001 *
)
{...}

PFND3D12DDI_CALCPRIVATECOMMANDQUEUESIZE_0001 


```

## -remarks

## -see-also

