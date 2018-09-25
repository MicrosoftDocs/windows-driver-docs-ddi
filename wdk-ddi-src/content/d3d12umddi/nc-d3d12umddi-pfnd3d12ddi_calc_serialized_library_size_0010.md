---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010
title: PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010
author: windows-driver-content
description: Calculates serialized library size.
ms.assetid: 40e47e56-5a99-431d-b821-a610a8c66601
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
-	PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CALC_SERIALIZED_LIBRARY_SIZE_0010 callback function

## -description

Calculates serialized library size.

## -prototype

```
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

## -parameters

### -param hDevice

A handle to a display device.

### -param hLibrary

A handle to a pipeline library.



## -returns

Returns SIZE_T.