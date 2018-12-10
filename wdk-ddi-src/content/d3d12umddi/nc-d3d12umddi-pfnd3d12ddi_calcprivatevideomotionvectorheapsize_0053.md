---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEOMOTIONVECTORHEAPSIZE_0053
title: PFND3D12DDI_CALCPRIVATEVIDEOMOTIONVECTORHEAPSIZE_0053
author: windows-driver-content
description: Calculates the video motion vector heap size.
ms.assetid: 88c05154-c3bb-46c3-8178-7ce94aa1f261
ms.date: 10/19/2018
ms.topic: callback
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
-	PFND3D12DDI_CALCPRIVATEVIDEOMOTIONVECTORHEAPSIZE_0053
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CALCPRIVATEVIDEOMOTIONVECTORHEAPSIZE_0053 callback function

## -description

Calculates the video motion vector heap size.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALCPRIVATEVIDEOMOTIONVECTORHEAPSIZE_0053 Pfnd3d12ddiCalcprivatevideomotionvectorheapsize0053; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivatevideomotionvectorheapsize0053 
(
	D3D12DDI_HDEVICE hDrvDevice
	CONST D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0053 *pArgs
)
{...}

```

## -parameters

### -param hDrvDevice

A handle to the display device (graphics context).

### -param *pArgs

Pointer to a [D3D12DDIARG_CREATE_VIDEO_MOTION_VECTOR_HEAP_0053](ns-d3d12umddi-d3d12ddiarg_create_video_motion_vector_heap_0053.md) structure.

## -returns

Returns SIZE_T.

## -remarks



## -see-also
