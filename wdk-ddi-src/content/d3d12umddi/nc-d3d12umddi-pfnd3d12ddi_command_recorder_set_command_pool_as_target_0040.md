---
UID: NC:d3d12umddi.PFND3D12DDI_COMMAND_RECORDER_SET_COMMAND_POOL_AS_TARGET_0040
title: PFND3D12DDI_COMMAND_RECORDER_SET_COMMAND_POOL_AS_TARGET_0040
author: windows-driver-content
description:
ms.assetid: 1b264f1f-635b-44dd-aa4c-0e28ca010a2b
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
-	PFND3D12DDI_COMMAND_RECORDER_SET_COMMAND_POOL_AS_TARGET_0040
product: Windows
targetos: Windows
---

# PFND3D12DDI_COMMAND_RECORDER_SET_COMMAND_POOL_AS_TARGET_0040 callback function

## -description

Implemented by the client driver to set the command pool as a target for the command recorder.

## -prototype

```
//Declaration

PFND3D12DDI_COMMAND_RECORDER_SET_COMMAND_POOL_AS_TARGET_0040 Pfnd3d12ddiCommandRecorderSetCommandPoolAsTarget0040;

// Definition

VOID Pfnd3d12ddiCommandRecorderSetCommandPoolAsTarget0040
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HCOMMANDRECORDER_0040
	 D3D12DDI_HCOMMANDPOOL_0040
)
{...}

PFND3D12DDI_COMMAND_RECORDER_SET_COMMAND_POOL_AS_TARGET_0040


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param D3D12DDI_HCOMMANDRECORDER_0040

A handle to the command recorder.

### -param D3D12DDI_HCOMMANDPOOL_0040

A handle to the command pool.



## -returns

This callback function does not return a value.



## -see-also