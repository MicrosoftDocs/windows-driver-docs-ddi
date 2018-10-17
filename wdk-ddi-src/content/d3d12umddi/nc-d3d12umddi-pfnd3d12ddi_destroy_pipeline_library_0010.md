---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROY_PIPELINE_LIBRARY_0010
title: PFND3D12DDI_DESTROY_PIPELINE_LIBRARY_0010
author: windows-driver-content
description: Destroys the pipeline library.
ms.assetid: c57be6ff-bfd1-4709-96a1-e4b9552c29b9
ms.date: 
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
-	PFND3D12DDI_DESTROY_PIPELINE_LIBRARY_0010
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_DESTROY_PIPELINE_LIBRARY_0010 callback function

## -description

Destroys the pipeline library.

## -prototype

```
//Declaration

PFND3D12DDI_DESTROY_PIPELINE_LIBRARY_0010 Pfnd3d12ddiDestroyPipelineLibrary0010; 

// Definition

VOID Pfnd3d12ddiDestroyPipelineLibrary0010 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HPIPELINELIBRARY
)
{...}

PFND3D12DDI_DESTROY_PIPELINE_LIBRARY_0010 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HPIPELINELIBRARY: 

A pipeline library handle.

## -returns

Returns VOID.

## -remarks




## -see-also
