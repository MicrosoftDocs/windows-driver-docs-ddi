---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0010
title: PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0010
author: windows-driver-content
description: Used to calculate the pipeline state size.
ms.assetid: 863bec8d-f609-46e0-baef-16978d9a0d44
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0010
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0010 callback function

## -description

Used to calculate the pipeline state size.

## -prototype

```
//Declaration

PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0010 Pfnd3d12ddiCalcPrivatePipelineStateSize0010; 

// Definition

SIZE_T Pfnd3d12ddiCalcPrivatePipelineStateSize0010 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_PIPELINE_STATE_0010 *
)
{...}

PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0010 


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param *

Used to create a pipeline state.

## -returns

The size in bytes of the state size.