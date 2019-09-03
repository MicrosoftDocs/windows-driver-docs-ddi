---
UID: NC:d3d12umddi.PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054
title: PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054
author: windows-driver-content
description: Queries for clock calibration information.
tech.root: display
ms.assetid: c9ce34e2-6d10-4746-aa81-7a49f65a364f
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054"
ms.prod: windows-hardware
ms.technology: windows-devices
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
 - PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0021, 19H1
---

# PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054 callback function

## -description

Queries for clock calibration information.

## -prototype

```
//Declaration

PFND3D12DDI_QUERY_CLOCK_CALIBRATION_0054 Pfnd3d12ddiQueryClockCalibration0054; 

// Definition

void Pfnd3d12ddiQueryClockCalibration0054 
(
	D3D12DDI_HDEVICE Arg1
	D3D12DDI_HCOMMANDQUEUE Arg2
	D3D12DDI_GPUCLOCKDATA_0054 *pClockData
)
{...}

```

## -parameters

### -param Arg1

The device to query clock information for.

### -param Arg2

A handle to the command queue.

### -param *pClockData

Pointer to a [D3D12DDI_GPUCLOCKDATA_0054](ns-d3d12umddi-d3d12ddi_gpuclockdata_0054.md) structure that contains the output frequency, GPU clock, and CPU clock on the specified engine.

## -returns

Returns void.

## -remarks


## -see-also
