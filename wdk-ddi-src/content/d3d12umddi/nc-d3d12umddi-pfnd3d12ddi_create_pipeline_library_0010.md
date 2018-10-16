---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PIPELINE_LIBRARY_0010
title: PFND3D12DDI_CREATE_PIPELINE_LIBRARY_0010
author: windows-driver-content
description: Create a pipeline library.
ms.assetid: 7c53cb2f-55a5-4777-b11d-c0bfc0e703f8
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
-	PFND3D12DDI_CREATE_PIPELINE_LIBRARY_0010
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CREATE_PIPELINE_LIBRARY_0010 callback function

## -description

Create a pipeline library.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CREATE_PIPELINE_LIBRARY_0010 Pfnd3d12ddiCreatePipelineLibrary0010; 

// Definition

HRESULT Pfnd3d12ddiCreatePipelineLibrary0010 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_PIPELINE_LIBRARY_0010 *
	 D3D12DDI_HPIPELINELIBRARY
)
{...}

PFND3D12DDI_CREATE_PIPELINE_LIBRARY_0010 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param *

Pointer to a D3D12DDIARG_CREATE_PIPELINE_LIBRARY_0010 structure.

### -param D3D12DDI_HPIPELINELIBRARY: 

A handle to a pipeline library.

## -returns

Returns HRESULT.
