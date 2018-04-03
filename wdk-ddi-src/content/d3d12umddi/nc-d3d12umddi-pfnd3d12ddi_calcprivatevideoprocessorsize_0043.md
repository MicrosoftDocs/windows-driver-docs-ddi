---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043
title: PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043
author: windows-driver-content
description:
ms.assetid: d3793818-114a-4668-af13-b2eedbb39577
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
-	PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043
product: Windows
targetos: Windows
---

# PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043 callback function

## -description

Used to calculate the size of a video processor.

## -prototype

```
//Declaration

PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043 Pfnd3d12ddiCalcprivatevideoprocessorsize0043;

// Definition

SIZE_T Pfnd3d12ddiCalcprivatevideoprocessorsize0043
(
	D3D12DDI_HDEVICE hDrvDevice
	CONST D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0043 *pArgs
)
{...}

PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0043


```

## -parameters

### -param hDrvDevice

A handle to the display device (graphics context).

### -param *pArgs [in]

The arguments used to create a video processor.

## -returns

Returns the size of the video processor in bytes.

## -remarks



## -see-also