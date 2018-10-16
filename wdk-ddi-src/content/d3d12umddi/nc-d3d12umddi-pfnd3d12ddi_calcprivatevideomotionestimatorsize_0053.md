---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEOMOTIONESTIMATORSIZE_0053
title: PFND3D12DDI_CALCPRIVATEVIDEOMOTIONESTIMATORSIZE_0053
author: windows-driver-content
description: Calculates the driver object size.
ms.assetid: 2980611e-51df-4c26-9453-34bddb3b00a1
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_CALCPRIVATEVIDEOMOTIONESTIMATORSIZE_0053
product:
-	Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CALCPRIVATEVIDEOMOTIONESTIMATORSIZE_0053 callback function

## -description

Calculates the driver object size. The Direct3D runtime allocates memory for storing the drivers CPU object representing the motion estimator.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATEVIDEOMOTIONESTIMATORSIZE_0053 Pfnd3d12ddiCalcprivatevideomotionestimatorsize0053; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivatevideomotionestimatorsize0053 
(
	D3D12DDI_HDEVICE hDrvDevice
	CONST D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0053 *pArgs
)
{...}

```

## -parameters

### -param hDrvDevice

A handle to the display device (graphics context) that the Direct3D runtime uses.

### -param *pArgs

Pointer to a [D3D12DDIARG_CREATE_VIDEO_MOTION_ESTIMATOR_0053](ns-d3d12umddi-d3d12ddiarg_create_video_motion_estimator_0053.md) structure.

## -returns

Returns SIZE_T.

## -remarks




## -see-also
