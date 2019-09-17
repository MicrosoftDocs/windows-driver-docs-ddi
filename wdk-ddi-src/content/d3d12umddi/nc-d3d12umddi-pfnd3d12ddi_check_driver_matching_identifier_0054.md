---
UID: NC:d3d12umddi.PFND3D12DDI_CHECK_DRIVER_MATCHING_IDENTIFIER_0054
title: PFND3D12DDI_CHECK_DRIVER_MATCHING_IDENTIFIER_0054 (d3d12umddi.h)
description: Checks the serialized driver identifier to see if it matches the specified device.
ms.assetid: 241eb409-0ff3-4638-bdc3-fe655e7b1e7d
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CHECK_DRIVER_MATCHING_IDENTIFIER_0054"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CHECK_DRIVER_MATCHING_IDENTIFIER_0054
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CHECK_DRIVER_MATCHING_IDENTIFIER_0054 callback function

## -description

Checks the serialized driver identifier to see if it matches the specified device.

## -parameters

### -param Arg1

A handle to the device.

### -param Arg2

Specifies the type of serialized data.

### -param Arg3

Pointer to a [D3D12DDI_SERIALIZED_DATA_DRIVER_MATCHING_IDENTIFIER_0054](ns-d3d12umddi-d3d12ddi_serialized_data_driver_matching_identifier_0054.md) structure.

## -returns

Returns [D3D12DDI_DRIVER_MATCHING_IDENTIFIER_STATUS](ne-d3d12umddi-d3d12ddi_driver_matching_identifier_status.md) that specifies whether the device is compatible with the serialized data.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CHECK_DRIVER_MATCHING_IDENTIFIER_0054 Pfnd3d12ddiCheckDriverMatchingIdentifier0054; 

// Definition

D3D12DDI_DRIVER_MATCHING_IDENTIFIER_STATUS Pfnd3d12ddiCheckDriverMatchingIdentifier0054 
(
	D3D12DDI_HDEVICE Arg1
	D3D12DDI_SERIALIZED_DATA_TYPE Arg2
	CONST D3D12DDI_SERIALIZED_DATA_DRIVER_MATCHING_IDENTIFIER_0054 *
)
{...}

```

## -remarks

## -see-also

