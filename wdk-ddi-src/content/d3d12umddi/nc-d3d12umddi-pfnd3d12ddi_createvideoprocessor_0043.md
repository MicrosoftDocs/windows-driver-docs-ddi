---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOPROCESSOR_0043
title: PFND3D12DDI_CREATEVIDEOPROCESSOR_0043 (d3d12umddi.h)
description: Used to create a video processor.
ms.assetid: 23658659-2c91-4257-ab20-ef3df15f1262
ms.date: 10/19/2018
ms.topic: callback
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
topic_type:
-	apiref
api_type:
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_CREATEVIDEOPROCESSOR_0043
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CREATEVIDEOPROCESSOR_0043 callback function

## -description

The <i>pfnCreateVideoProcessor</i> callback function creates a video processor.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATEVIDEOPROCESSOR_0043 Pfnd3d12ddiCreatevideoprocessor0043;

// Definition

HRESULT Pfnd3d12ddiCreatevideoprocessor0043
(
	D3D12DDI_HDEVICE hDrvDevice
	CONST D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0043 *pArgs
	D3D12DDI_HVIDEOPROCESSOR_0020 hDrvVideoProcessor
)
{...}

PFND3D12DDI_CREATEVIDEOPROCESSOR_0043


```

## -parameters

### -param hDrvDevice

A handle to the display device (graphics context).

### -param *pArgs

The arguments used to create a video processor.

### -param hDrvVideoProcessor

The video processor.

## -returns

Returns STATUS_SUCCESS if completed successfully.

## -remarks

Register your implementation of this callback function by setting the appropriate member of D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0043 and then calling Pfnd3d12ddiCreatevideoprocessor0043.


## -see-also
