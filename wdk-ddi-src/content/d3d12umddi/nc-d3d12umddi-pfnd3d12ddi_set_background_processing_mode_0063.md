---
UID: NC:d3d12umddi.PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0063
title: PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0063
author: windows-driver-content
description: When an application changes background processing mode, PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0063 is called to inform the UMD of the new settings.
tech.root: display
ms.assetid: 2f87c644-756d-4fcf-b3a5-7b0a636e8203
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0063"
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
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
 - apiref
api_type: 
 - UserDefined
api_location: 
 - d3d12umddi.h
api_name: 
 - PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0063
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: D3D12 Release 6, Build rev 3., 19H1
---

# PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0063 callback function

## -description

When an application changes background processing mode, PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0063 is called to inform the UMD of the new settings.

## -prototype

```
//Declaration

PFND3D12DDI_SET_BACKGROUND_PROCESSING_MODE_0063 Pfnd3d12ddiSetBackgroundProcessingMode0063; 

// Definition

void Pfnd3d12ddiSetBackgroundProcessingMode0063 
(
	D3D12DDI_HDEVICE hRTDevice
	D3D12DDI_BACKGROUND_PROCESSING_MODE_0062 Mode
	D3D12DDI_MEASUREMENTS_ACTION_0062 MeasurementsAction
	BOOL *pbFurtherMeasurementsDesired
)
{...}

```

## -parameters

### -param hRTDevice

[in] The handle of the device for the driver to use when it calls back into the runtime.

### -param Mode

A [D3D12DDI_BACKGROUND_PROCESSING_MODE_0062](ne-d3d12umddi-d3d12ddi_background_processing_mode_0062.md) enumeration that represents the background processing mode.

### -param MeasurementsAction

A [D3D12DDI_MEASUREMENTS_ACTION_0062](ne-d3d12umddi-d3d12ddi_measurements_action_0062.md) enumeration that represents the measurement action.

### -param *pbFurtherMeasurementsDesired

Pointer to a BOOL, indicating whether further measurements are desired.

## -returns

Returns void.

## -remarks

Background processing work must only ever be used for optimization purposes. These work items must not affect functional correctness of the implementation.


## -see-also
