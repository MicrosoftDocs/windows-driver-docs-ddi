---
UID: NC:d3d12umddi.PFND3D12DDI_OPENHEAPANDRESOURCE_0003
title: PFND3D12DDI_OPENHEAPANDRESOURCE_0003
author: windows-driver-content
description: Implemented by the client driver to open heap and resource.
ms.assetid: aca4ecce-657a-4288-b761-2c6463d039d8
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_OPENHEAPANDRESOURCE_0003
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_OPENHEAPANDRESOURCE_0003 callback function

## -description

Implemented by the client driver to open heap and resource.

## -prototype

```cpp
//Declaration

PFND3D12DDI_OPENHEAPANDRESOURCE_0003 Pfnd3d12ddiOpenheapandresource0003; 

// Definition

HRESULT Pfnd3d12ddiOpenheapandresource0003 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_OPENHEAP_0003 *
	 D3D12DDI_HHEAP
	 D3D12DDI_HRTRESOURCE
	 D3D12DDI_HRESOURCE
)
{...}

PFND3D12DDI_OPENHEAPANDRESOURCE_0003 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param * 

Pointer to a D3D12DDIARG_OPENHEAP_0003 structure.

### -param D3D12DDI_HHEAP 

A heap handle.

### -param D3D12DDI_HRTRESOURCE 

The handle of the resource for the driver to use when it calls back into the runtime.

### -param D3D12DDI_HRESOURCE 

A resource handle.



## -returns

Returns HRESULT.

## -remarks




## -see-also
