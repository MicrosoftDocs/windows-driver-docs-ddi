---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040
title: PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040
author: windows-driver-content
description:
ms.assetid: 3220b5c8-7911-41fc-a698-5163a61ad60a
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	apiref
apitype:
-	UserDefined
apilocation:
-	d3d12umddi.h
apiname:
-	PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040
product: Windows
targetos: Windows
---

# PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040 callback function

## -description

Implemented by the client driver to calculate the command recorder size.

## -prototype

```
//Declaration

PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040 Pfnd3d12ddiCalcPrivateCommandRecorderSize0040;

// Definition

SIZE_T Pfnd3d12ddiCalcPrivateCommandRecorderSize0040
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_COMMAND_RECORDER_0040 *
)
{...}

PFND3D12DDI_CALC_PRIVATE_COMMAND_RECORDER_SIZE_0040


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param D3D12DDIARG_CREATE_COMMAND_RECORDER_0040 *

Pointer to a D3D12DDIARG_CREATE_COMMAND_RECORDER_0040 structure that contains the arguments to create a command recorder.

## -returns

Returns SIZE_T that represents the size of the command recorder.



## -see-also