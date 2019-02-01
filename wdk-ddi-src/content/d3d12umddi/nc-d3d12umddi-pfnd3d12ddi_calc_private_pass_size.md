---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_PASS_SIZE
title: PFND3D12DDI_CALC_PRIVATE_PASS_SIZE (d3d12umddi.h)
description: Used in the creation of a pass.
tech.root: display
ms.assetid: 1ec7e11f-fd5b-43a5-88a0-45b819ebc2e0
ms.date: 11/28/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver: D3D12DDI_SUPPORTED_0020
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
 - PFND3D12DDI_CALC_PRIVATE_PASS_SIZE
product: 
 - Windows
targetos: Windows
---

# PFND3D12DDI_CALC_PRIVATE_PASS_SIZE callback function

## -description

Used in the creation of a pass.

## -prototype

```
//Declaration

PFND3D12DDI_CALC_PRIVATE_PASS_SIZE Pfnd3d12ddiCalcPrivatePassSize; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivatePassSize 
(
	D3D12DDI_HDEVICE Arg1
	 const D3D12DDIARG_CREATE_PASS *
)
{...}

```

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param *

A pointer to the D3D12DDIARG_CREATE_PASS structure that contains arguments used to create a pass.

## -returns

Returns SIZE_T.

## -remarks

This callback is used as part of a test to see if drivers can find perf wins from being told when apps are repeating "passes" of consistent workloads. The app instructs the driver to observe how some passes run and gives the driver a chance to make optimizations for future runs of the same pass. The contents of a "pass" can be anything - it is up to the app to be relatively consistent in the overall performance characteristics of a pass.


## -see-also
