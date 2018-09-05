---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYHEAPANDRESOURCE
title: PFND3D12DDI_DESTROYHEAPANDRESOURCE
author: windows-driver-content
description: 
ms.assetid: 12c5cdc3-981a-4a34-af3c-b62ff7872877
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
-	PFND3D12DDI_DESTROYHEAPANDRESOURCE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_DESTROYHEAPANDRESOURCE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_DESTROYHEAPANDRESOURCE Pfnd3d12ddiDestroyheapandresource; 

// Definition

VOID Pfnd3d12ddiDestroyheapandresource 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HHEAP
	 D3D12DDI_HRESOURCE
)
{...}

PFND3D12DDI_DESTROYHEAPANDRESOURCE 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param D3D12DDI_HHEAP: 
### -param D3D12DDI_HRESOURCE: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also