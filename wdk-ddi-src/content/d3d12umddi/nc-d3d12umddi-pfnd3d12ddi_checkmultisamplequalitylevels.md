---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS
title: PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS (d3d12umddi.h)
description: Implemented by the client driver to check multi-sample quality levels.
ms.assetid: 50197de3-654f-47d1-9213-d10ac78c0299
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS callback function

## -description

Implemented by the client driver to check multi-sample quality levels.

## -parameters

### -param hDevice

A handle to a device.

### -param Format

A DXGI_FORMAT.

### -param SampleCount

The sample count.

### -param Flags

Multi-sample quality level flags.

### -param pNumQualityLevels

The number of quality levels.

## -returns

Returns VOID.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS Pfnd3d12ddiCheckmultisamplequalitylevels;

// Definition

VOID Pfnd3d12ddiCheckmultisamplequalitylevels
(
	D3D12DDI_HDEVICE hDevice
	DXGI_FORMAT Format
	UINT SampleCount
	D3D12DDI_MULTISAMPLE_QUALITY_LEVEL_FLAGS Flags
	UINT *pNumQualityLevels
)
{...}

PFND3D12DDI_CHECKMULTISAMPLEQUALITYLEVELS


```

