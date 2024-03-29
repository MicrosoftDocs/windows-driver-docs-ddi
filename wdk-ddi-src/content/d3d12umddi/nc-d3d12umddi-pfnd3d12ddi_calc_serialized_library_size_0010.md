---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010
title: PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010 (d3d12umddi.h)
description: Calculates serialized library size.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010 callback function"]
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
 - PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010
 - d3d12umddi/PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010
dev_langs:
 - c++
---

# PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010 callback function


## -description

Calculates serialized library size.

## -parameters

### -param hDevice

A handle to a display device.

### -param hLibrary

A handle to a pipeline library.

## -returns

Returns SIZE_T.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010 Pfnd3d12ddiCalcSerializedLibrarySize0010; 

// Definition

SIZE_T Pfnd3d12ddiCalcSerializedLibrarySize0010 
(
	D3D12DDI_HDEVICE hDevice
	D3D12DDI_HPIPELINELIBRARY hLibrary
)
{...}

PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010 


```

